# 第三方服务

「Material」主题内置了多种第三方服务，并且可以轻松的启用。

## RSS

安装插件：[hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed)，配置方式如插件 `README.md` 所示。
然后在 [url: rss](config/basic?id=url) 中添加生成的 feed 路径。

## topPost

使用该插件可以将指定文章置顶。
如果您需要这个功能，请使用 `npm install hexo-helper-post-top --save` 安装支持插件。
之后在您需要置顶文章的 `front-matter` 中，添加 `top: true` 即可置顶。

----

在 **主题配置文件** 中定位到 `Integrated Services` 即可进行第三方服务的配置。

## 评论系统

定位到 **`主题配置文件`** 中 `Integrated Services` 的 `comment`，即可以设置评论。

### Disqus

Material 主题提供了两种使用 [Disqus](https://disqus.com/) 主题的方式，在 **主题配置文件** 中填写 `comment: use: ` 字段，值设置为 `disqus` 或 `disqus_click`。

> 使用 Disqus_Click 时，文章页面不会主动加载 Disqus 评论，直到按下按钮。这项设置有助于改善处在 **`公开、平等、有序 的 网络审查 地区`** 下的浏览者的体验。

在 `comment: shortname: ` 填入你的 Disqus shortname

----

需要注意的是此处的 `shortname` 不是你的登录的 id，是你的评论二级域名去掉 `.duoshuo.com` 或 `.disqus.com` 部分

>例如：Disqus 域名 `example.disqus.com`

> ```yaml
shortname: example
```

### 畅言

使用 [畅言](http://changyan.kuaizhan.com)，需在 **主题配置文件** 中填写 `comment: use: ` 字段，值设置为 `changyan`。

- changyan_appid: 畅言的 APPID
- changyan_conf: 畅言的 CONF
- changyan_thread_key_type: path #用于设置畅言的 tread key，默认为 path。

### 来必力

> Material 主题内置的来必力是 `city_verision`

使用 来必力，需在 **主题配置文件** 中填写 `comment: use: ` 字段，值设置为 `livere`。
打开来必力后台中找到 “获取代码”，在 WEB 代码中，找到 `data-uid`，填入到 **主题配置文件** 中评论系统的配置的 `livere_data_uid: `

### Gitment

使用 Gitment，需在 **主题配置文件** 中填写 `comment: use: ` 字段，值设置为 `gitment`。
根据 [gitment 的文档](https://github.com/imsun/gitment/blob/master/README.md) 完成 GitHub Oauth App 的申请并获取 key。
然后在主题配置文件中填入 `gitment_repo`  `gitment_owner` `gitment_client_id` 完成配置即可。

### Valine

Valine 是一款基于 Leancloud 的 sdk 开发的评论系统。使用 Valine，需在 **主题配置文件** 中填写 `comment: use: ` 字段，值设置为 `valine`。
根据 [Valine 的文档](https://github.com/xCss/Valine/blob/master/README.md) 完成 Leancloud 端的配置，然后填充下列参数。

- `valine_leancloud_appId`：Leancloud 的 APPID
- `valine_leancloud_appKey`：Leancloud 的 APPKey
- `valine_notify`：true | false。Valine 的评论邮件提醒功能，请阅读 [Vailne Wiki 有关部分](https://github.com/xCss/Valine/wiki/Valine-%E8%AF%84%E8%AE%BA%E7%B3%BB%E7%BB%9F%E4%B8%AD%E7%9A%84%E9%82%AE%E4%BB%B6%E6%8F%90%E9%86%92%E8%AE%BE%E7%BD%AE) 
- `valine_placeholder`：没有评论时评论框显示的提示语

### Gittalk

[Gitalk](https://gitalk.github.io) 和 Gitment 一样都是一个基于 GitHub Issue 的评论系统。在完成 GitHub Oauth App 的申请并获取 key 后，在主题配置文件中填入 `gitalk_repo` `gitalk_owner` `gitalk_client_id` `gitalk_client_secret` 参数即可。

## 搜索系统

Material 主题内置了 `google ` `swiftype` `local` 三种搜索系统。

```yaml
- use
- swiftype_key
```

### Google

调用 Google 搜索引擎对您的站点进行搜索。

在 **主题配置文件** 中修改 `search: use` 的值为 `google` 即可。

### 本地搜索

使用本地搜索需要安装 [hexo-generator-search](https://github.com/PaicHyperionDev/hexo-generator-search) 插件。

然后在 `站点配置` 文件中添加
```yaml
search:
	path: search.xml
	field: all
```

### Swiftype

注册 [Swiftype](https://swiftype.com/)，然后在 **主题配置文件** 中修改 `search: use` 的值为 `swiftype`，并填入你的 `swiftype_key`。

> 在你的 `Swiftype Install Code` 中，有这么一行代码 `_st('install','*****','2.0.0');` 。其中 `*****` 即为 `swiftype_key`

## 数据统计与分析

用于设置访客分析服务，支持 Google Analysis 、百度站长工具和 CNZZ。

- `xxxx_site_id`: 站点统计 ID

### 百度统计

登录 [百度统计](http://tongji.baidu.com/)，在站点的代码获取页面复制 `` 后面那串统计脚本 id，填入 `baidu_site_id`。

### Google 分析

在 `google_site_id` 字段填入你的 Google 跟踪 ID。跟踪 ID 通常是以 UA- 开头。

### CNZZ

在 `cnzz_site_id `填入 CNZZ 提供的统计的站点 ID。 这个 ID 可以在地址栏里，或者自动生成的脚本里面找到。

> 在 CNZZ 提供的统计代码中，`z_stat.php?id=` 后和 `&web_id=` 各有一串字符，它们应该是相同的。将这串字符填入 `site_id`。

为避免影响美观，Material 主题使用 `display: none;`隐藏了“站长统计”几个字。

### 其它统计服务

确保 上述配置的字段为空，然后在在 `head.yml` 中填入你的统计服务代码。如何使用 `head.yml`，请访问[进阶设定](/expert/)中关于 自定义代码 的部分。

### PV&UV 统计

在 Material 主题中提供 PV&UV 显示。

#### Leancloud

```yaml
- enable: 默认为 false。
- app_id: APP ID。
- app_key: APP Key。
- av_core_mini: 统计 js。
```

打开 LeanCloud 官网，进入[注册页面](https://leancloud.cn/login.html#/signup)注册。完成邮箱激活后，点击头像，进入控制台页面

创建一个新应用 (默认类型为JavaScript SDK)，点击应用进入；

创建名称为 `Counter` 的 Class
注意：`ACL 权限` 必须为 `无限制`

编辑 `主题配置文件` ，修改 `leancloud` 条目，将 `enable` 改为 `true`，再填入 `app_id` 与 `app_key`。在 `应用->设置->应用 Key` 可看到 `APP ID` 与 `APP Key`

> 为了保证应用的统计计数功能仅应用于自己的博客系统，你可以在 `应用->设置->安全中心` 的Web安全域名中加入自己的博客域名，以保证数据的调用安全。

#### 不蒜子

```yaml
- enable: 默认为 false。
- all_site_uv: 默认为 false。
- post_pv: 默认为 false。
- busuanzi_pure_mini_js: 统计 js。
```

使用 不蒜子 浏览次数统计，仅需在 **主题配置文件** 中将 `busuanzi: enable: ` 的值设置为 `true`。

其中：

- `all_site_uv` 可统计全站的独立访客人数，即可在 `blog_info` 模块的 `Menu` 菜单中看到。
- `post_pv` 统计每篇文章的页面浏览次数，在文章页的 `分享按钮` 菜单中可看到。
- `busuanzi_pure_mini_js` 调用不蒜子统计 js 文件，可将该文件保存至你的 WebServer 或 CDN 中，然后在这里填入 URL。
