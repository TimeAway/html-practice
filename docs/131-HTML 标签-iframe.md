# HTML 标签 - `iframe`

`<iframe>` 是 HTML 内联框架元素，它能够将另一个 HTML 页面嵌入到当前页面中。

每个嵌入的 `<iframe>`，都会有自己的会话历史记录和 DOM 树，不过增加 `<iframe>` 也会增加内存和其他计算资源，因为
其拥有完整的文档环境，所以在增加 `<iframe>` 的同时也要考虑性能问题。

## 1. `allow` 属性

用于为 `<iframe>` 指定其特征策略。

### 1.1 `allow=fullscreen`

用于代替 `allowfullscreen=true` 属性，用于激活 `<iframe>` 的全屏模式。

### 1.2 `allow=payment`

用于代替 `allowpaymentrequest=true` 属性，用于跨域的 `<iframe>` 调用 `Payment Request API`

## 2. `csp` 属性

对嵌入的资源配置内容安全策略。

## 3. `width`、`heigth` 属性

指定 `<iframe>` 的宽高，可指定数字，单位像素；也可指定百分比。默认宽 300px，高 150px。

## 4. `importance` 属性

表示 `<iframe>` 的 `src` 属性指定的资源的加载优先级。

- `auto` 默认值，不指定优先级，浏览器根据自身情况决定。

- `high` 优先级高

- `low` 优先级低

## 5. `name` 属性

用于定位嵌入的 `<iframe>` 的名称，该名称可以用作 `<a>` 标签 与 `<form>` 标签的 `target`
属性值，也可以用作 `<input>` 标签和 `<button>` 标签的 `formtarget` 属性值，还可以用作
`window.open()` 方法的 `windowName` 参数值。

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

## 7. `sandbox` 属性

该属性对呈现在 iframe 框架中的内容启用一些额外的限制条件。

属性值可以为空字符串（这种情况下会启用所有限制），也可以是用空格分隔的一系列指定的字符串。有效的值有：

- `allow-downloads-without-user-activation` : 允许在没有征求用户同意的情况下下载文件.
- `allow-forms`: 允许嵌入的浏览上下文提交表单。如果没有使用该关键字，则无法提交表单。
- `allow-modals`: 允许嵌入的浏览上下文打开模态窗口。
- `allow-orientation-lock`: 允许嵌入的浏览上下文锁定屏幕方向（译者注：比如智能手机、平板电脑的水平朝向或垂直朝向）。
- `allow-pointer-lock`: 允许嵌入的浏览上下文使用 Pointer Lock API.
- `allow-popups`: 允许弹窗 (例如 window.open, target="\_blank", showModalDialog)。如果没有使用该关键字，相应的功能将自动被禁用。
- `allow-popups-to-escape-sandbox`: 允许沙箱化的文档打开新窗口，并且新窗口不会继承沙箱标记。例如，安全地沙箱化一个广告页面，而不会在广告链接到的新页面中启用相同的限制条件。
- `allow-presentation`: 允许嵌入的浏览上下文开始一个 presentation session。
- `allow-same-origin`: 如果没有使用该关键字，嵌入的浏览上下文将被视为来自一个独立的源，这将使 same-origin policy 同源检查失败。
- `allow-scripts`: 允许嵌入的浏览上下文运行脚本（但不能创建弹窗）。如果没有使用该关键字，就无法运行脚本。
- `allow-storage-access-by-user-activation` : 允许嵌入的浏览上下文通过 Storage Access API 使用父级浏览上下文的存储功能。
- `allow-top-navigation`: 允许嵌入的浏览上下文导航（加载）内容到顶级的浏览上下文。
- `allow-top-navigation-by-user-activation`: 允许嵌入的浏览上下文在经过用户允许后导航（加载）内容到顶级的浏览上下文。

## 8. `src` 属性

被嵌套的页面的 URL 地址。使用 `about:blank` 值可以嵌入一个遵从同源策略的空白页。

## 9. `srcdoc` 属性

该属性是一段 HTML 代码，这些代码会被渲染到 iframe 中。如果浏览器不支持 `srcdoc` 属性，则会渲染 `src` 属性表示的内容。

```html
<iframe
  src="https://mdn-samples.mozilla.org/snippets/html/iframe-simple-contents.html"
  title="iframe example 1"
  width="400"
  height="300"
>
  <p>Your browser does not support iframes.</p>
</iframe>
```
