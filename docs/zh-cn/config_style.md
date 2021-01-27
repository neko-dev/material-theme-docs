# 样式设定

## scheme

Material 主题提供了多种分支主题外观，亦称「Scheme」。
目前 Material 内置两种 Scheme：

### Paradox

默认 Scheme，是 Material 的最初样式。居中布局，图文并茂。

### Isolation

Paradox 的至简样式，简洁明了。

----

Scheme 的切换通过更改 **主题配置文件**，搜索 `scheme` 关键字。 你会看到有几行 scheme 的配置，将你需用启用的 scheme 去掉前面注释 `#` 即可。

> 例如 - 选择 Paradox Scheme

>```yaml
#scheme: Nexus
scheme: Paradox
#scheme: Isolation
```

## uiux

用于设置主题 UI 与 UX。

- slogan: 显示在 `blog_info` 模块中的标语，你可以设置单行标语或者多行标语：

> 单行标语使用
> ```yaml
  slogan: 标语（支持 HTML 标签）
```

> 多行标语使用
> ```yaml
  slogan:
   - "标语第一行"
   - "标语第二行"
   - "标语第三行"
```

- theme_color: 主题主要颜色。主题的大部分地方使用此颜色。
- theme_sub_color: 主题辅助颜色。
- hyperlink_color: 超链接颜色。
- button_color: 按钮颜色，例如 `toTop` 或 `menu_button`。
- android_chrome_color: 安卓 Chrome 浏览器的地址栏颜色。
- nprogress_color: 页面加载时顶部加载进度条的颜色。
- nprogress_buffer: 页面加载时顶部加载进度条的缓冲时间。

> [Color palette](https://material.google.com/style/color.html#color-color-palette)
> 符合 Material Design 的规范颜色。

## js_effect

用来控制 Material 主题中自带的多种 js 特性。

- fade: 页面加载时部分模块的渐显效果，默认为 true。
- smoothscroll: 页面平滑滚动特效，默认为 false。

## reading

用于设置阅读体验。

- entry_excerpt: 首页文章输出摘要的字符长度。默认为 80。

> 注意，这里设定的字符长度包括 `Front-Matter` 的长度，但是在首页，`Front-Matter` 不会显示出来。

## thumbnail

用于设置文章缩略图相关。

- purecolor: 填入颜色代码。如果文章内无设置缩略图，此项又不为空，则使用纯色缩略图。
- random_amount: 随机图片数量，根据 `主题所在文件夹/source/img/random` 中的图片数量设置。Material 主题默认提供了 19 张 Material 风格的缩略图。

## background

用于设置站点背景。

- purecolor: 填入颜色代码。则站点使用纯色背景。
- bgimg: 背景地址，默认调用 `主题文件夹 -> source -> img` 中的 `bg.png`。可更换此图片或者自己填入 url。
- bing: 用于启用“必应美图”的图片作为背景。
    - `parameter`:
        - `color=`: black, blue, brown, green, multi, orange, pink, purple, red, white, yellow.
        - `type=`: A (动物), C (人文), N (自然), S (太空), T (旅行).

## img

用于设置站点图片。

- logo: 显示于 `blog_info` 模块中。
- avatar: 你的头像设置。
- daily_pic: 显示于 `daily_pic` 模块中。
- sidebar_header: 显示于 `sidebar` 顶部。
- footerico: 设置 `footer` 中 SNS 图标的路径。
- random_thumbnail: 随机缩略图的路径。
- footer_image: 你可以在侧边栏底部放置任何你想要的图片。

以又拍云联盟图标为例，你可以这样配置：

```yaml
footer_image:
    upyun_logo:
        link: "https://www.upyun.com/"
        src: "/img/upyun_logo.svg"
```

## fonts

- `family`: 用于设置站点的字体。

> `fonts.family` 默认值为 `Roboto, "Helvetica Neue", Helvetica, "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "微软雅黑", Arial, sans-serif`
> 该字体设定为 Material Design 的规范，如无特殊要求 无需额外修改。
> 当你修改字体时，请在 `head.yml` 内使用 `<link>` 标签引用你的字体源。如何使用 `head.yml`，请访问[进阶设定](/expert/)中关于 自定义代码 的部分。

- `use`: 用于设置站点字体的引用方式。Material 主题内置了以下三种字体库支持。除此以外，你也可以手动设定你喜欢的谷歌字体反代服务。
  - `google`: 使用 Google 字体库加载 `Roboto` 字体。
  - `ustc`: 使用中科大反代的 Google 字体库加载 `Roboto` 字体。
  - `baomitu`: 使用 360 前端团队 奇舞团 维护的字体库加载 `Roboto` 字体。
  - `custom`, 使用你喜欢的谷歌字体镜像服务加载 `Roboto` 字体。使用该选项需要在 `custom_font_host` 中填入字体库的 URL

> **注意！`custom_font_host` 中设定的字体库的 URL 需要带 proctol（如 https://）且末尾不能带 `/` ！**

## card_elevation

用来设置主题卡片阴影。
