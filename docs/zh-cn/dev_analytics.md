# 站点访问统计适配指南

在 Material 主题 1.4.0 版本的开发过程中，我们重构了网站访问统计系统的插入方案，从而为贡献者和用户适配更多网站统计服务提供了便利。

## 目录结构

在 `layout/_widget/analytics` 目录下有多个 ejs 文件，`{name}-analytics.ejs`

> {name} 是统计服务的名称，如 `baidu`、`google`、`cnzz`

该 ejs 会在 `<head>` 标签前被加入。

## 适配方法

新建一个 ejs，名为 `{name}-analytics.ejs`。
在该统计服务的后台获得代码，并粘贴在其中。
修改主题配置文件中的 `analytics: use:` 字段为文件名中的 {name} 即可调用。

> 注意！确保适配后的通用性，请将 ID 等变量设计为可以从外部配置的。在 Material 主题中，从主题配置文件中调用站点 ID 配置的变量是 <%= theme.analytics.site_id %>。如果你需要额外的配置变量需要插入到主题配置文件等（如 Piwik 站点统计系统的 `piwik.js` 目录、Piwik 服务域名等），请阅读 Hexo 的 API 文档。

---

> 如果想具体了解我们的站点访问统计功能是如何实现调用的，参见 Pull Request #326，了解 1.4.0 版本中评论系统重构的细节。
