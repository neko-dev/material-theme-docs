# 自定义

## copyright_since

用于设置站点成立的时间。

> 例如，如果你设置了 2015，那么 footer 就会显示 `© 2015 - 2017`。

如果这个值为空，那么 footer 只会显示现在的年份。

## footer_text

你可以在页面的 Footer 指定你想显示的文字，支持 HTML 标签；默认为空。
比如，备案号可以这样设定：

```yaml
footer_text: '<a href="http://www.miitbeian.gov.cn" rel="nofollow">某ICP备xxxxxxxx号-x</a>'
```

## Code

使用 `Google Prettify` 或 `hanabi` 实现代码高亮。你只能启用他们中的一个。
启用之前你需要禁用 Hexo 自带的代码高亮。

```yaml
# Available value for `prettify` or `hanabi`: true | false
# You can only enable one of them to avoid issues. Also you need to check highlight option in _config.yml. Make sure that default hexo built in highlight plugin is disabled.
#        highlight:
#            enable: false
#
#     Prettify
#         theme value:
#         theme-name  # /vendors/prettify/themes/[theme-name].css
prettify:
  enable: false
  theme: "vibrant-ink" # default value: "vibrant-ink"   # theme-name without '.css'
#     Hanabi
#         hanabi © egoist, Released under the MIT License
#         https://github.com/egoist/hanabi
#     
#     line_number: [true/false] # Show line number for code block
#     includeDefaultColors: [true/false] # Use default hanabi colors
#     customColors:     # This value accept a string or am array to setting for hanabi colors.
#                       # If `includeDefaultColors` is true, this will append colors to the color pool
#                       # If `includeDefaultColors` is false, this will instead default color pool
hanabi:
    enable: false
    line_number: true
    includeDefaultColors: true
    customColors: 
```

`hanabi.customColors` 中添加多种自定义颜色作为代码高亮主题时请遵循 Yaml 的规范填写配置。

## Post License

你可以在每篇文章的结尾添加你的版权说明，支持 HTML 标签。License 以粗体显示，默认为空。
比如，你可这样设定 CC License。

```yaml
license: 'This blog is under a <a href="/creativecommons.html" target="_blank">CC BY-NC-SA 3.0 Unported License</a>'
```
> 你也可以在页面的 Front-Matter 中为不同文章添加不同的 License。

## Qrcode

用于在文章页中显示二维码，扫描二维码即可直接打开文章。

- enable: 是否显示二维码
- use: 设置生成二维码的方式，可选的有：plugin | online

> 当 `use` 设置为 `plugin` 时，你需要安装 `hexo-helper-qrcode` 插件，使用 `npm install hexo-helper-qrcode --save` 安装。
> 当 `use` 设置为 `online` 时，二维码将会由 `pan.baidu.com` 的 API 生成。
