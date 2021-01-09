# HTML 标签 - `script`

`<script>` 元素用于嵌入或引用可执行脚本。这通常用作嵌入或者指向 JavaScript 代码。

`<script>` 元素也能在其他语言中使用，比如 WebGL 的 GLSL 着色器语言。

```html
<!-- HTML4 and (x)HTML -->
<script type="text/javascript" src="javascript.js">

  <!-- HTML5 -->
  <script src="javascript.js">
</script>
```

## 1. `async` 属性

布尔值，该属性能够消除解析阻塞的 Javascript。

对于普通脚本，如果存在 `async` 属性，那么普通脚本会被并行请求，并尽快解析和执行。

对于模块脚本，如果存在 `async` 属性，那么脚本及其所有依赖都会在延缓队列中执行，
因此它们会被并行请求，并尽快解析和执行。

## 2. `defer` 属性

这个布尔属性被设定用来通知浏览器该脚本将在文档完成解析后，触发 DOMContentLoaded 事件前执行。

有 `defer` 属性的脚本会阻止 DOMContentLoaded 事件，直到脚本被加载并且解析完成。

## 3. `crossorigin` 属性

可以使用本属性来使那些将静态资源放在另外一个域名的站点打印错误信息。

## 4. `integrity` 属性

包含用户代理可用于验证已提取资源是否已无意外操作的内联元数据。

## 5. `nomodule` 属性

这个布尔属性被设置来标明这个脚本在支持 ES2015 modules 的浏览器中不执行。

## 6. `referrerpolicy` 属性

表示在获取 iframe 资源时如何发送 referrer 首部：

- `no-referrer`: 不发送 Referer 首部。

- `no-referrer-when-downgrade` (default): 向不受 TLS (HTTPS) 保护的 origin 发送请求时，
  不发送 Referer 首部。

- `origin`: referrer 首部中仅包含来源页面的源。换言之，仅包含来源页面的 scheme, host, 以及
  port。

- `origin-when-cross-origin`: 发起跨域请求时，仅在 referrer 中包含来源页面的源。发起同源
  请求时，仍然会在 referrer 中包含来源页面在服务器上的路径信息。

- `same-origin`: 对于 same origin （同源）请求，发送 referrer 首部，否则不发送。

- `strict-origin`: 仅当被请求页面和来源页面具有相同的协议安全等级时才发送 referrer 首部
  （比如从采用 HTTPS 协议的页面请求另一个采用 HTTPS 协议的页面）。如果被请求页面的协议安全
  等级较低，则不会发送 referrer 首部（比如从采用 HTTPS 协议的页面请求采用 HTTP 协议的页面）。

- `strict-origin-when-cross-origin`: 当发起同源请求时，在 referrer 首部中包含完整的 URL。
  当被请求页面与来源页面不同源但是有相同协议安全等级时（比如 HTTPS→HTTPS），在 referrer
  首部中仅包含来源页面的源。当被请求页面的协议安全等级较低时（比如 HTTPS→HTTP），不发送 referrer 首部。

- `unsafe-url`: 始终在 referrer 首部中包含源以及路径 （但不包括 fragment，密码，或用户名）。
  这个值是不安全的, 因为这样做会暴露受 TLS 保护的资源的源和路径信息。

## 7. `src` 属性

这个属性定义引用外部脚本的 URI，这可以用来代替直接在文档中嵌入脚本。

指定了 src 属性的 script 元素标签内不应该再有嵌入的脚本。

## 8. `type` 属性

该属性定义 script 元素包含或 src 引用的脚本语言。属性的值为 MIME 类型;

支持的 MIME 类型包括：`text/javascript`, `text/ecmascript`, `application/javascript`, 和 `application/ecmascript`。

如果没有定义这个属性，脚本会被视作 JavaScript。

## 9. `text` 属性

和 textContent 属性类似，本属性用于设置元素的文本内容。但和 textContent 不一样的是，
本属性在节点插入到 DOM 之后，此属性被解析为可执行代码。
