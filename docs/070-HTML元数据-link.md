# HTML 元数据 - 外部资源链接元素 `<link>`

规定了当前文档与外部资源的关系。该元素最常用于链接样式表，此外也可以被用来创建站点图标
(比如 PC 端的 `favicon` 图标和移动设备上用以显示在主屏幕的图标) 。

## 1. 属性

### 1.1 `as` 属性

`as` 属性只有在 `<link>` 元素设置了 `rel="preload"` 时才能使用。它规定了 `<link>` 元素加载
的内容类型，对于内容的优先级、请求匹配、正确的内容安全策略的选择以及正确的 Accept 请求头的设置，
这个属性是必需的。

其值如下：

| 值         | 应用场景                                                                                                         |
| ---------- | ---------------------------------------------------------------------------------------------------------------- |
| `audio`    | `<audio>` 元素                                                                                                   |
| `document` | `<iframe>` 和 `<frame>` 元素                                                                                     |
| `embed`    | `<embed>`                                                                                                        |
| `fetch`    | `fetch` 和 `XHR`，如果使用该值，那么 `<link>` 同时必须包含 `crossorigin` 属性                                    |
| `font`     | `CSS` 的 `@font-face`                                                                                            |
| `image`    | 设置了 `srcset` 或者 `imageset` 属性的 `<img>`、`<picture>` 元素，`svg` 的 `image` 元素，`CSS` 的 `*-image` 规则 |
| `object`   | `<object>` 元素                                                                                                  |
| `script`   | `<script>` 元素，`Worker` 的 `importScripts` 属性                                                                |
| `style`    | `<link rel=stylesheet>` 元素，`CSS` 的 `@import`                                                                 |
| `track`    | `<track>` 元素                                                                                                   |
| `video`    | `<video>` 元素                                                                                                   |
| `worker`   | `Worker` 和 `SharedWorker`                                                                                       |

### 1.2 `crossorign` 属性

`crossorign` 属性指定在加载相关资源时是否必须使用 CORS。当不设置此属性时, 资源将会不使用 CORS 加载 (即不发送 Origin: HTTP 头)。

`crossorign` 属性可设置如下值：

- `anonymous`
  会发起一个跨域请求(即包含 Origin: HTTP 头).
  但不会发送任何认证信息 (即不发送 cookie, X.509 证书和 HTTP 基本认证信息).
  如果服务器没有给出源站凭证 (不设置 Access-Control-Allow-Origin: HTTP 头), 资源就会被污染并限制使用.
- `use-credentials`
  会发起一个带有认证信息 (发送 cookie, X.509 证书和 HTTP 基本认证信息) 的跨域请求 (即包含 Origin: HTTP 头).
  如果服务器没有给出源站凭证 (不设置 Access-Control-Allow-Origin: HTTP 头), 资源就会被污染并限制使用.

### 1.3 `disabled` 属性

`disabled` 属性仅对于 `rel="stylesheet"`。
如果在加载 HTML 时在 HTML 中指定了 Disabled， 则在页面加载期间不会加载样式表。
相反，如果禁用属性更改为 false 或删除时，样式表将按需加载。

```html
<link disabled rel="alternate stylesheet" href="css/pooh" />

<script>
  document.querySelector("link").removeAttribute("disabled");
</script>
```

### 1.4 `href` 属性

此属性指定被链接资源的 URL。 URL 可以是绝对的，也可以是相对的。

### 1.5 `hreflang` 属性

此属性指明了被链接资源的语言. 其意义仅供参考。仅当设置了 `href` 属性时才应设置该属性。

### 1.6 `importance` 属性

指示资源的相对重要性。只有存在 `rel=“preload”` 或 `rel=“prefetch” `时，`importance` 属性才能用于 `<link>` 元素。

优先级如下：

- `auto`: 表示没有偏好。 浏览器可以使用其自己的启发式方法来确定资源的优先级。

- `high`: 向浏览器指示资源具有高优先级。

- `low`: 向浏览器指示资源的优先级较低。

### 1.7 `integrity` 属性

`integrity` 包含行内元数据，它是一个你用浏览器获取的资源文件的哈希值，以 `base64` 编码的方式加的密，
这样用户能用它来验证一个获取到的资源,在传送时未被非法篡改。

### 1.8 `media` 属性

这个属性规定了外部资源适用的媒体类型。它的值必须是"媒体查询"。这个属性使得用户代理能选择最适合设备运行的媒体类型。
值可参考 [媒体查询列表](https://whatwg-cn.github.io/html/#valid-media-query-list)

### 1.9 `referrerpolicy` 属性

指示在获取资源时使用哪个引荐来源网址。

- 'no-referrer' 表示 Referer 标头将不会发送。
- 'no-referrer-when-downgrade' 的原始位置时不会发送任何 Referer 标头。 如果未指定其他政策，这是用户代理的默认行为。
- 'origin' 意味着引荐来源网址将是页面的来源，大致是方案，主机和端口。

- 'origin-when-cross-origin' 这意味着导航到其他来源将仅限于方案，主机和端口，而在同一来源上导航将包括引荐来源网址的路径。
- 'unsafe-url' 意味着引荐来源网址将包含来源和路径（但不包括片段，密码或用户名）。 这种情况是不安全的，
  因为它可能会将来源和路径从受 TLS 保护的资源泄漏到不安全的来源。

### 2.0 `rel` 属性

表示当前文档与目标资源之间的关系。其属性值为链接类型，可以是多个，多个之间用空格隔开。

具体使用参考：[rel 链接类型](071-HTML的rel链接类型.md)

### 2.1 `sizes` 属性

这个属性定义了包含相应资源的可视化媒体中的 icons 的大小。 它只有在 rel 包含 icon 的 link 类型值。

具体使用参考：[浏览器图标，favicon的使用](073-浏览器图标favicon的介绍与使用.md)

### 2.2 `title` 属性

属性在<link>元素上有特殊的语义。当用于<link rel="stylesheet">时，它定义了一个首选样式表或备用样式表。

### 2.3 `type` 属性

这个属性被用于定义链接的内容的类型。这个属性的值应该是像 text/html，text/css 等 合法的 MIME 类型。
这个属性常用的用法是定义链接的样式表，最常用的值是表明了 CSS 的 text/css。
对于外部资源链接，type 属性用于提示用户代理避免获取它们不支持的资源。

参考：[MIME 类型](https://mimesniff.spec.whatwg.org/#mime-type) 

## 2. 引入一个外部样式表

```html
<link href="main.css" rel="stylesheet" />
```

## 3. 通过媒体查询有条件地加载资源

```html
<link href="print.css" rel="stylesheet" media="print">

<link href="mobile.css" rel="stylesheet" media="all">

<link href="desktop.css" rel="stylesheet" media="screen and (min-width: 600px)">

<link href="highres.css" rel="stylesheet" media="screen and (min-resolution: 300dpi)">
```

## 4. 样式表加载事件

```html
<script>
function sheetLoaded() {
  // Do something interesting; the sheet has been loaded
}

function sheetError() {
  alert("An error occurred loading the stylesheet!");
}
</script>

<link rel="stylesheet" href="mystylesheet.css" onload="sheetLoaded()" onerror="sheetError()">
```
