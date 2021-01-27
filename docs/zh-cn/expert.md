# 进阶使用

> 以下部分可能影响到「Material」主题的正常运作，请务必先了解这些设定背后的相关知识。

-----

## 添加自定义代码

如果想要在站点的 `<head>` 之前添加自定义 `font-face` 或者统计代码（例如 `Piwik Analytics`）。

需要在 hexo 目录下的 `source` 文件夹内创建一个名为 `_data`（禁止改名）的文件夹，并在文件内创建一个名为 `head.yml` 的文件。

单个代码格式为：

```yaml
Name:
	"put your code here"
```

代码将显示在 `</head>` 之前。

---

如果想要在站点的 `</body>` 之前添加自定义代码（例如 `Service Worker`）。

需要在 hexo 目录下的 `source` 文件夹内创建一个名为 `_data`（禁止改名）的文件夹，并在文件内创建一个名为 `footer.yml` 的文件。
单个代码格式为：

```yaml
Name:
	"put your code here"
```

代码将显示在 `</body>` 之前。

## Material 图标

用于自定义例如 `dropdown: icon` 的图标。

[Material icons](https://material.io/icons/)

## 代码高亮样式

从 `1.3.0` 版本开始，您可以使用 `hexo-prism-plugin` 进行代码染色，具体文档请参阅 [Hexo-Prism-Plugin 插件文档](https://github.com/ele828/hexo-prism-plugin)
从 `1.4.5` 版本开始，您可以使用主题内置的 `Google Prettify` 进行代码染色。具体文档请参阅主题配置。
从 `1.5.0` 版本开始，您可以使用主题内置的 `Hanabi` 进行代码染色。具体文档请参阅主题配置。

## 使用 CDN

定位到 **主题配置文件** 进行配置。

### MaterialCDN

现在你可以使用 CDN 来加速 Material 主题引用的静态文件，只需要在 `materialcdn` 中填入你的 CDN 的 URL 路径即可。默认为空、从网站源站加载。

> **注意！填入的 URL 末尾不需要带 `/` ！**

例如，您可以这么配置：

```yaml
vendors:
    materialcdn:  https://cdn.jsdelivr.net/gh/viosey/hexo-theme-material@latest/source
```

> 您可以使用由 [jsDelivr](https://www.jsdelivr.com) 提供的公共 CDN 加速您的博客。

------

Material 主题引用了下述第三方库，你可以使用公共 CDN 库加载它们。
Material 主题使用的第三方库包括：

###  jQuery 2.2.0
### FontAwesome 4.5.0

> 你需要填入 css 的 URI，如：`https://cdn.bootcss.com/font-awesome/4.5.0/css/font-awesome.min.css`

### MathJax 2.7.0-2.7.1

> 你不需要在 URI 中带上 MathJax 的 query 配置。主题会自动在你填入的 URI 后面加上。

### nprogress 0.2.0
### Prettify r298

> 仅加载 `prettify.js`。代码高亮的主题将从本地或者 MaterialCDN 中加载。

### Material Icons 3.0.1

> 你需要填入 css 的 URI，如：`https://cdn.bootcss.com/material-design-icons/3.0.1/iconfont/material-icons.min.css`
