# 独立页面

## 创建「友情链接」页面

### 创建页面
在 hexo 目录下的 `source` 文件夹内创建一个名为 `links`（只是建议，可根据自己喜好修改）的文件夹。

然后在文件内创建一个名为 `index.md` 的 Markdown 文件。

在 `index.md` 文件内写入如下内容即可。
```markdown
---
title: links
date:
layout: links
---
```
>`title` 可修改，`layout` 不可修改。

如果想添加「友情链接」页面的入口，请参考 [独立页面](/intro/#pages)。

### 添加数据
同样在在 hexo 目录下的 `source` 文件夹内创建一个名为 `_data`（禁止改名）的文件夹。

然后在文件内创建一个名为 `links.yml` 的文件。

单个友情链接的格式为：

```yaml
Name:
    link: http://example.com
    avatar: http://example.com/avatar.png
    descr: "这是一个描述"
```

>添加多个友情链接，只需要根据上面的格式重复填写即可。

- 将 `Name` 改为友情链接的名字，例如 `Viosey`。
- `http://example.com` 为友情链接的地址。
- `http://example.com/avatar.png` 为友情链接的头像。
- `这是一个描述` 为友情链接描述。


## 创建「图库」页面

### 创建页面
在 hexo 目录下的 `source` 文件夹内创建一个名为 `gallery`（只是建议，可根据自己喜好修改）的文件夹。

然后在文件内创建一个名为 `index.md` 的 Markdown 文件。

在 `index.md` 文件内写入如下内容即可。
```markdown
---
title: gallery
date:
layout: gallery
---
```
>`title` 可修改，`layout` 不可修改。

如果想添加「图库」页面的入口，请参考 [独立页面](/intro/#pages)。

### 添加数据
同样在在 hexo 目录下的 `source` 文件夹内创建一个名为 `_data`（禁止改名）的文件夹。

然后在文件内创建一个名为 `gallery.yml` 的文件。

单个图片的格式为：

```yaml
Name:
	full_link: http://example.com/full-image.png
	thumb_link: http://example.com/thumb-image.png
	descr: "这是一个描述"
```
>添加多张图片，只需要根据上面的格式重复填写即可。

- 将 `Name` 改为图片名字，例如 `Material`。
- `http://example.com/full-image.png` 为完整图片的地址。
- `http://example.com/thumb-image.png` 为图片缩略图的地址，如果没有缩略图也可使用完整图片的地址。
- `这是一个描述` 为图片描述。


## 创建「标签云」页面

### 创建页面

在 hexo 目录下的 `source` 文件夹内创建一个名为 `tags`（只是建议，可根据自己喜好修改）的文件夹。

然后在文件内创建一个名为 `index.md` 的 Markdown 文件。

在 `index.md` 文件内写入如下内容即可。
```markdown
---
title: tags
date:
layout: tags
---
```
>`title` 可修改，`layout` 不可修改。

如果想添加「标签云」页面的入口，请参考 [独立页面](/intro/#pages)。

## 创建「时间轴」页面

### 创建页面

在 hexo 目录下的 `source` 文件夹内创建一个名为 `timeline`（只是建议，可根据自己喜好修改）的文件夹。

然后在文件内创建一个名为 `index.md` 的 Markdown 文件。

在 `index.md` 文件内写入如下内容即可。
```markdown
---
title: timeline
date:
layout: timeline
---
```
>`title` 可修改，`layout` 不可修改。

如果想添加「标签云」页面的入口，请参考 [独立页面](/intro/#pages)。