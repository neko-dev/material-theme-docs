# 评论系统适配指南

在 Material 主题 1.4.0 版本的开发过程中，我们重构了评论系统的插入方案，从而为适配评论系统提供了便利。

## 目录结构

在 `layout/_widget/comment` 目录下设有多个子目录，以评论系统命名，如 `disqus` `changyan` `disqus_proxy`。
每个子目录下有三个 ejs 文件，分别是 `enter.ejs` `common.ejs` `main.ejs`。

### enter

`enter.ejs` 用于插入评论框。这个部分由包裹评论框的 `<div>` 标签、和定义评论框的外部样式的 `<style>` 标签组成。

### main

`main.ejs` 是评论框的组成部分。这一部分一般会包含有评论框的配置部分，用于生成并插入评论框。

### common

`common.ejs` 是评论框的基础代码部分；每个评论系统都有自己的公共代码部分，比如引用外来 JS 文件等。

---

`enter.ejs` 插入在 Post 页面的评论框的位置，`main.ejs` 由 `enter.ejs` 调用。`common.ejs` 调用于页面底部的 `footer-option.ejs`。

## 适配方法

Fork 项目到你的 Repo，Clone 回你的本地，以 `canary` 为基础 Fork 一份新的分支。

> 分支的命名和 commit 的命名方法，请阅读 [Material
 主题开发规范](https://github.com/viosey/hexo-theme-material/wiki)

以多说为例，我们展示一下如何将有关代码插入到三个不同的 ejs 中，实现给主题适配多说评论系统。

这是多说后台提供的安装代码如下：

```html
<!-- 多说评论框 start -->
	<div class="ds-thread" data-thread-key="请将此处替换成文章在你的站点中的ID" data-title="请替换成文章的标题" data-url="请替换成文章的网址"></div>
<!-- 多说评论框 end -->
<!-- 多说公共JS代码 start (一个网页只需插入一次) -->
<script type="text/javascript">
var duoshuoQuery = {short_name:"SHORTNAME"};
	(function() {
		var ds = document.createElement('script');
		ds.type = 'text/javascript';ds.async = true;
		ds.src = (document.location.protocol == 'https:' ? 'https:' : 'http:') + '//static.duoshuo.com/embed.js';
		ds.charset = 'UTF-8';
		(document.getElementsByTagName('head')[0] 
		 || document.getElementsByTagName('body')[0]).appendChild(ds);
	})();
	</script>
<!-- 多说公共JS代码 end -->
```

可以看到，多说的安装代码由两个部分组成，评论框部分和公共代码部分。

在 `layout/_widget/comment` 下新建一个目录，这里以 `duoshuo-dev` 为例，新建一个子目录 `duoshuo-dev`。
在 `duoshuo-dev` 下新建三个 ejs 文件分别命名为 `common.ejs`、`enter.ejs`、`main.ejs`。

在 `enter.ejs` 中填入以下内容：

```ejs
<div id="{name}-comment">
    <%- partial('_widget/comment/' + theme.comment.use + '/main') %>
</div>
<style>
    #{name}-comment{
        background-color: #eee;
        padding: 2pc;
    }
</style> 
```

其中 `{name}` 即评论系统的名字。在这里，我们保持与子目录名字一致的原则，命名为 `duoshuo-dev`。
其中 `<style>` 标签定义了评论框的背景颜色和边距。

在 `main.ejs` 中填入多说评论框的有关代码。

```ejs
<!-- 多说评论框 start -->
    <div class="ds-thread" data-thread-key="请将此处替换成文章在你的站点中的ID" data-title="请替换成文章的标题" data-url="请替换成文章的网址"></div>
<!-- 多说评论框 end -->
```

请注意，这里的变量请使用 Hexo 的有关变量替换。Hexo 提供了调用当前页面 URL、页面标题等 API。除此以外，在 Front-Matter 调用一些变量也是可行的方案。

> 如果你需要在插入额外的代码、文字或者样式，也可以在 `main.ejs` 插入。以 Material 主题实际适配多说的工作中，我们为多说设计了一套 Material 的样式 `duoshuo.css`，我们就在这里使用 `<link>` 标签引用了该样式。

在 `common.ejs` 中，填入公共代码部分：

```ejs
<!-- 多说公共JS代码 start (一个网页只需插入一次) -->
<script type="text/javascript">
var duoshuoQuery = {short_name:"SHORTNAME"};
	(function() {
		var ds = document.createElement('script');
		ds.type = 'text/javascript';ds.async = true;
		ds.src = (document.location.protocol == 'https:' ? 'https:' : 'http:') + '//static.duoshuo.com/embed.js';
		ds.charset = 'UTF-8';
		(document.getElementsByTagName('head')[0] 
		 || document.getElementsByTagName('body')[0]).appendChild(ds);
	})();
	</script>
<!-- 多说公共JS代码 end -->
```

注意！确保适配后的通用性，请将 shortname 等变量设计为可以从外部配置的。在 Material 主题中，从主题配置文件中调用配置的 shortname 的变量是 `<%= theme.comment.shortname %>`。如果你需要额外的配置变量需要插入到主题配置文件等（如畅言评论系统需要 APP_ID 和 CONF 配置），请阅读 Hexo 的 API 文档。

接下来，在主题配置文件中，`comment: use:` 字段，填入 `duoshuo-dev` 字段，主题便会调用位于 `layout/_widget/comment/duoshuo-dev` 下的三个 ejs 文件，生成并插入评论框和有关代码。

将你的成果 Push 回你的 Repo，并 Open a Pull Request，我们 review 后会将你的改动合并回上游。

---

> 如果想具体了解我们的评论框是如何调用和插入页面的，参见 Pull Request [#311](https://github.com/viosey/hexo-theme-material/pull/311)，了解 1.4.0 版本中评论系统重构的细节。
