# 开始创作

## 创建文章

### 使用命令行
```shell
hexo new <title>
```

### 手动创建
在 hexo 主目录下 `source -> _posts` 新建以 `.md` 为后缀的文件。

## Front-matter

[Front-matter - 官方介绍](https://hexo.io/zh-cn/docs/front-matter.html)

| 参数          | 描述                | 默认值       |
|:--            |:--                  |:--           |
| `layout`      | 布局                | post         |
| `title`       | 标题                | 文件名       |
| `date`        | 建立日期            | 文件建立日期 |
| `updated`     | 更新日期            | 文件更新日期 |
| `tags`        | 标签（不适用于分页）|              |
| `categories`  | 分类（不适用于分页）|              |
| `permalink`   | 覆盖文章网址        |              |
| `thumbnail`   | 缩略图地址          |              |
| `toc`         | 显示 TOC 按钮       | true         |
| `comment`     | 显示评论            | true         |
| `notag`       | 不生成标签按钮      | false        |
| `top`         | 置顶                | false        |
| `mathJax`         | 启用 Mathjax       | false        |

注1：置顶功能请参考 [topPost](/intro/#topPost)

## 缩略图功能

在 Material 主题中，每个 Scheme 都有缩略图功能。
只需要在 `Front-matter` 中添加参数 `thumbnail: `，然后填入缩略图地址即可。

### Paradox

此 Scheme 如果没有自定义缩略图，则使用默认随机缩略图，随机缩略图目录位于主题文件夹下 `source -> img -> random`。
随机缩略图可添加自己喜好的图片，格式为 `<num>.png` 。然后在 **主题配置文件** 中 `thumbnail:random_amount` 修改缩略图数量。

### Isolation

此 Scheme 只会显示已自定义缩略图。

如果想添加自定义页面的入口，请参考 [独立页面](/intro/#pages)。
