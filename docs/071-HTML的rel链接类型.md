# HTML 的链接类型

HTML 的链接主要分为外部资源链接和超链接。可通过指定 `<a>`, `<area>` 或 `<link>` 元素使一个页面链接到另一个页面。

下面是 `<a>`, `<area>` 或 `<link>` 的 `rel` 属性对应的链接类型及其在 HTML 中的意义：

## 1. `alternate` 类型

**支持的元素**：`<a>`、`<area>`、`<link>`

`<link>` 的 `alternate` 定义了一个可替换的样式表，它和第一个 `<link>` 元素同时使用，
第一个定义了首选样式，而 `alternate` 则让用户可选择替换的样式。

- 如果是 `<link>` 元素，并且 `rel` 属性包括 `stylesheet`, 则这个 link 定义为 `alternate` 样式表;
  此时 `title` 属性不能为空.
  
```html
<!--  “页面样式” 菜单中会出现“Default Style”、“Fancy”和“Basic”的选项。 -->
<link href="reset.css" rel="stylesheet" type="text/css">

<link href="default.css" rel="stylesheet" type="text/css" title="Default Style">
<link href="fancy.css" rel="alternate stylesheet" type="text/css" title="Fancy">
<link href="basic.css" rel="alternate stylesheet" type="text/css" title="Basic">
```

- 如果 `type` 设置为 `application/rss+xml` 或者 `application/atom+xml`,
  则 link 被定义为 syndication feed. 页面中第一个被定义的为默认的。

- 其它情况 `link` 定义为 `alternate` 页面:
  - 另一种介质,例如手持设备(如果设置了 media 属性),
  - 另一种语言 (如果设置了 hreflang 属性),
  - 另一种格式, 例如 PDF (如果设置了 type 属性),
  - 或者是以上这些的集合.

## 2. `archives` 类型（避免使用）

**支持的元素**：`<a>`、`<area>`、`<link>`

定义文档的超链接，该文档包含此文件的存档链接. 例如. 一个博客入口可以链接到每月索引页面。

## 3. `author` 类型

**支持的元素**：`<a>`、`<area>`、`<link>`

定义一个超链接到一个描述作者信息的页面或者提供一个方法联系作者。

## 4. `bookmark` 类型

**支持的元素**：`<a>`、`<area>`

表明这个链接是一个固定链接，对于最近的 `<article>` 祖先标签. 如果没有，则表最近的 `section` 标签
`bookmark` 允许标识一个包括多个文档的页面，例如每月汇总的博客页面，或者博客集合。

## 5. `canonical` 类型

**支持的元素**：`<link>`

规范链接元素是一个 HTML 元素，它通过指定 web 页面的“规范”或“首选”版本作为搜索引擎优化的一部分，
帮助网站管理员防止重复的内容问题。

例如：在 `https://example.com/page.php?parameter=1` 页面告诉搜索引擎 `https://example.com/page.php` 该网页是首选版本。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="canonical" href="https://example.com/page.php" />
  </head>
  <body>
    ...
  </body>
</html>
```

```http request
HTTP/1.1 200 OK
Content-Type: application/pdf
Link: <https://example.com/page.php>; rel="canonical"
Content-Length: 4223
```

## 6. `dns-prefetch` 类型

**支持的元素**：`<link>`

提示浏览器该资源需要在用户点击链接之前进行 DNS 查询和协议握手。

## 7. `external` 类型

**支持的元素**：`<a>`、`<area>`

表明这个链接，是一个相对于当前网站的外部资源。点击这个链接会离开当前网站。

## 8. `first`, `last`, `prev`, `next` 类型（避免使用）

**支持的元素**：`<a>`、`<area>`、`<link>`

表明这个链接是当前页面资源序列中的顺序。

## 9. `help` 类型

**支持的元素**：`<a>`、`<area>`、`<link>`

- 如果是一个 `<a>` 或者 `<area>` 标签, `help` 表明这个链接，链接到一个关于父亲标签和它的后代的进一步帮助资源;

- 如果是一个 `<link>` 标签，`help` 表明这个链接，链接到一个关于整个页面的进一步帮助资源。

## 10. `icon` 类型

**支持的元素**：`<link>`

定义一个在用户界面上代表这个页面的资源，通常是一个图标（包括声音和图像）

`media`, `type` 和 `sizes` 属性允许浏览器选择其上下文中最合适的图标.如果多种资源符合条件，浏览器会选择最后一个。

苹果 iOS 不支持此链接类型, 也不支持 `sizes` 属性, 就像其他移动端浏览器一样，
为了 Web Clip 或者启动点位符选择一个页面图标。分别可使用不是标准方法的 `apple-touch-icon` 和 `apple-touch-startup-image` 替代.

具体使用参考：[浏览器图标，favicon的使用](073-浏览器图标favicon的介绍与使用.md)

**在之前，经常可以看到 shortcut，但他不是标准的，应该不再使用。**

## 10. `license` 类型（避免使用）

**支持的元素**：`<a>`、`<area>`、`<link>`

表示超链接指向描述许可信息的文档。 如果不在<head>元素内，则该标准不会区分应用于文档特定部分或整个文档的超链接。
仅页面上的数据可以表明这一点。

## 11. `manifest` 类型

**支持的元素**：`<link>`

表示链接到的文件是 Web App Manifest。

```html
<link rel="manifest" href="/manifest.json" />
```

## 12. `modulepreload` 类型

**支持的元素**：`<link>`

更早和更高优先级的加载模块脚本

## 13. `nofollow` 类型

**支持的元素**：`<a>`、`<area>`

表示本文档的作者不想宣传链接的文档，例如，它是不受控的，它是一个坏的例子或如果它们有商业关系（销售环节）。
`nofollow` 主要是被一些使用人气排名技术的搜索引擎所使用。

## 14. `noopener` 类型

**支持的元素**：`<a>`、`<area>`

指示浏览器打开链接而不授予新的浏览上下文对打开它的文档的访问权限-通过在打开的窗口中不设置 Window.opener 属性（返回 null）。

注意，使用 `noopener` 时，在决定是否打开新窗口/选项卡方面，除 `_top`，`_self` 和 `_parent` 以外的非空目标名称都被视为 `_blank`。

## 15. `noreferrer` 属性

**支持的元素**：`<a>`、`<area>`

阻止浏览器导航到另一个页面时，通过 Referer：HTTP header 将该页面地址或任何其他值作为 Referrer 发送。

## 16. `opener` 属性

**支持的元素**：`<a>`、`<area>`、`<form>`

恢复带有 `target="_blank"` 的链接上的隐式 `rel="noopener"`。

## 17. `pingback` 属性

**支持的元素**：`<link>`

定义一个外部资源 URI，以便在对该网页发表评论或引用时调用。 在 Pingback 1.0 规范中定义了用于进行此类调用的协议。

## 18. `preconnect` 属性

**支持的元素**：`<link>`

向浏览器提供提示，建议浏览器提前打开与链接网站的连接，而不会泄露任何私人信息或下载任何内容，以便在跟随链接时可以更快地获取链接内容。

## 19. `prefetch` 属性

**支持的元素**：`<link>`

链接预取是一种浏览器机制，其利用浏览器空闲时间来下载或预取用户在不久的将来可能访问的文档。
网页向浏览器提供一组预取提示，并在浏览器完成当前页面的加载后开始静默地拉取指定的文档并将其存储在缓存中。
当用户访问其中一个预取文档时，便可以快速的从浏览器缓存中得到。

参考：<https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Link_prefetching_FAQ>

## 20. `preload` 属性

**支持的元素**：`<link>`

表示用户十分有可能需要在当前浏览中加载目标资源，所以浏览器必须预先获取和缓存对应资源。

参考：[通过 rel='preload' 进行内容预加载](05-通过rel=%22preload%22进行内容预加载.md)

## 21. `prerender` 属性

**支持的元素**：`<link>`

建议浏览器事先获取链接的资源，并建议将预取的内容显示在屏幕外，以便在需要时可以将其快速呈现给用户。

## 22. `search` 属性

**支持的元素**：`<a>`、`<area>`、`<link>`

表示超链接引用了一个文档，该文档的接口专门设计用于在此文档或站点及其资源中进行搜索。

如果将 `type` 属性设置为 `application/opensearchdescription+xml`，则该资源是 OpenSearch 插件，
可以轻松将其添加到 Firefox 或 Internet Explorer 等某些浏览器的界面中。

## 23. `shortlink` 属性

**支持的元素**：`<link>`

一些网站创建短链接，使通过即时消息共享链接更容易。

## 24. stylesheet 属性

**支持的元素**：`<link>`

定义要用作样式表的外部资源。如果没有设置 `type`，在进一步检查之前，浏览器应该假定它是 `text/css` 样式表。

## 25. `tag` 属性

**支持的元素**：`<a>`、`<area>`

指示超链接引用了描述适用于该文档的标签的文档。

**注意**：不应在标签云的链接成员上设置此链接类型，因为这些链接对象不适用于单个文档，而不适用于一组页面。
