# 浏览器图标 favicon 的介绍与使用

## 1. favicon 的概述

favicon 是一个与网站、网页或网络应用程序相关联的小图标或图标集合。它可能会展示在浏览器的选项卡中、
收藏夹中、历史记录中、快捷方式等。

favicon 有利于用户更容易识别网站或品牌，所以设置 favicon 是非常有必要的。

网站图标的存在可以间接影响 SEO。一些搜索引擎（例如 DuckDuckGo）会在搜索结果中显示收藏夹图标。
引人注目的网站图标可以帮助提高这些搜索引擎的点击率（CTR）。此外，网站图标是建立品牌知名度和品牌信任度的必备条件。
缺少网站图标可能会导致用户对网站失去信任并增加跳出率。

## 2. favicon 支持的格式

最常见的网站图标格式是 ICO，PNG 和 SVG，但是还有针对特定浏览器或设备的其他格式。

### 2.1 ICO 格式 - favicon.icon

ICO 文件格式由 Microsoft 开发，是网站图标的原始文件格式。该格式是唯一的，因为它允许在同一文件中包含多个小图像。
这是有利的，因为 ICO 格式的图标图标（16x16、32x32 和 48x48 像素）所需的小图标可以独立缩放和优化。
在较小的尺寸下，您不能依靠浏览器以最佳方式自动调整图标的大小。
ICO 格式受所有浏览器支持，并且是 IE5 至 IE10 支持的唯一格式。

### 2.2 PNG 格式 - favicon.png

PNG 格式是一种很好的格式，因为它是大多数人习惯的格式，不需要任何特殊工具即可创建。
随着现代屏幕具有高分辨率，用于小分辨率的小图标尺寸的原始问题不再存在。
对于支持 PNG Favicon 格式的浏览器，通常在浏览器选项卡或书签栏中显示的 Favicon 的质量将高于 ICO 格式。
PNG 格式的缺点是它与 IE5 到 IE10 不兼容。

### 2.3 SVG 格式 - favicon.svg

SVG 格式具有优于 PNG 和 ICO 格式的优点，但还没有强大的浏览器支持。
SVG 文件非常轻巧，并且可以无限扩展。这意味着在不牺牲图像加载时间的情况下，图像质量极佳。
仅 Chrome，Firefox 和 Opera 支持 SVG 格式的图标。

## 3. 常用网站图标的大小

务必注意，favicon 图标必须是正方形的。

对于 ICO 格式，建议的尺寸为 16x16、32x32 和 48x48 像素。

对于 PNG 格式，建议的尺寸为 16x16 和 32x32 像素，但浏览器将接受任何方形 PNG 图片。

## 4. favicon 的使用

```html
<link rel="apple-touch-icon" sizes="180x180" href="/apple-touch-icon.png" />

<link rel="icon" type="image/png" sizes="32x32" href="/favicon-32x32.png" />

<link rel="icon" type="image/png" sizes="16x16" href="/favicon-16x16.png" />

<link rel="manifest" href="/site.manifest" />
```
