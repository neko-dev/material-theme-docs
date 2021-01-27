# 菜单配置

## toc

是否显示 TOC(Table of Content) 菜单中的行号。

## sns

用于填写你的 SNS 信息，其中 `email` 会显示在侧边栏，其他信息会以按钮的形式显示在 `footer`。

- email
- twitter
- facebook
- googleplus
- weibo
- instagram
- tumblr
- github
- linkedin
- facebook

## sns_share

用于定义分享菜单中的项目， `false` 的项将不会显示在分享菜单中。

- twitter
- googleplus
- weibo
- linkedin
- qq
- telegram

## sidebar

### dropdown
用于设置 Paradox 侧边栏用户下拉菜单，默认为空。

>参考配置样式

>```yaml
dropdown:
	Email Me:
		link: "mailto: someone@example.com"
		icon: email
```


### homepage

设置 “主页” 按钮

```yaml
use: 设置 true 时会在侧边栏显示 “主页” 按钮.
icon: 在 “主页” 前面显示一个 Material 图标。为空和被注释时则不显示.
divider: 设置成 true
archives
```

### archives

用来设置归档下拉菜单。

```yaml
use: 设置成 true 时在侧边栏显示归档。
icon: 为归档添加一个 Material Icon，注释掉或为空则不显示 Icon
divider: 设置成 true 后会在归档按钮底部增加一条分割线。
```

### categories

用来设置分类显示按钮。

```yaml
use: 设为 true 在侧边栏显示分类按钮。
icon: 在分类按钮前显示一个 Material Icon，注释掉或为空则不显示 Icon
divider: 设置成 true 后会在归档按钮底部增加一条分割线。
```

### pages

用于设置独立页面的入口，默认为空。填写条目后独立页面入口将显示在：

- `logo card` 的 `Page` 按钮下拉菜单中。(Scheme Paradox)
- 侧边栏。(Scheme Paradox)
- 站点左侧。(Scheme Isolation)

请按照如下样例添加个人独立页面。 

```yaml
pages:
    About:
        link: "#about"
        icon: person
        divider: false
```

作为一个单位。

- Name 是该独立页面的名称，请自行修改。
- link 的参数为相对路径，对应 hexo 目录下的 `source` 文件夹内的相应文件夹。
- icon 的参数为自定义的 Material 图标，可用图标可在 [Material icons](https://material.io/icons/) 查询。
- divider 设置成 true 后会在该条目底部增加一条分割线

### article_num

在主题的侧边栏显示文章总数。

```yaml
use: 设置成 true 时会在侧边栏显示文章总数。
divider: 设置成 true 后会在该条目底部增加一条分割线。
```

### footer

配置侧边栏的底部

```yaml
divider: 设置成 true 后会在侧边栏底部之前增加一条分割线。
theme: 设置成 true 后会在侧边栏底部增加一个指向 Material 主题的链接。
```
