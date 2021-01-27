# 基本设定

## Language

编辑 **站点配置文件**，将 `language` 设置成你所需要的语言。
可用的语言如下：

- العَرَبِيَّة (ar)
- Deutsch (de)
- English (en)
- Español (es)
- Français (fr)
- 日本語 (ja)
- Malay (ms)
- Portuguese (Brazil) (pt-BR)
- 简体中文 (zh-CN)
- 繁體中文 (zh-TW)


>例如：选用繁體中文，则配置为：

```yaml
language: zh-TW
```

## Site Information

### head

用于配置生成的 HTML 文件的头部信息。

- `favicon`: 网站的 favicon
- `high_res_favicon`: 高清 favicon
- `apple_touch_icon`: iOS 主屏按钮图标
- `keywords`: 网站关键词
- `site_verification`: 搜索引擎验证
  - `google`: 谷歌 Search Console 验证
  - `baidu`: 百度站长平台验证

> 向搜索引擎验证你对站点的所有权，用于向搜索引擎提交 sitemap 和管理站点被搜索引擎收录的情况
> 1. 登录搜索引擎后台，选择使用 `HTML 标记` 验证站点所有权，搜索引擎后台会给你一串类似于这样的东西：
```html
<meta name="xxxx-site-verification" content="xxxxxxxxxxxxxxxxxxxxxxxxxxxx" />
```
> 2. 将 `xxxxxxxxxxxxxxxxxxxxxxxxxxxx` 字符串复制出来，填入对应搜索引擎的设置中，博客更新以后即可通过验证。

- `structured_data`: 启用后会在页面的 head 中生成结构化数据，有助于改善 Google 等搜索引擎的 SEO。这项功能需要你完善地配置主题的 **`站点配置文件`** 和 **`主题配置文件`**，所以如果你在 `hexo g` 中出现问题，尝试禁用该选项。默认值为 true.

### url

用于设置跳转链接。

- rss: 设置生成的 rss 或 atom url
- daily_pic: 设置 `daily_pic` 模块 点击时跳转的 url
- logo: 设置 logo 点击时跳转的 url

> 如何使用 RSS，请访问文档的[集成服务](/service/)，获取启用 RSS 的方法。
