# HTML 元数据 - 文档级元素 `<meta>`

`<meta>` 简单的来说就是描述数据的数据。
例如, 一个 HTML 文件是一种数据, 但 HTML 文件也能在 `<head>` 元素中包含描述该文档的元数据，比如该文件的作者和概要。

meta 元素定义的元数据的类型包括以下几种：

- 如果设置了 `name` 属性，meta 元素提供的是文档级别（document-level）的元数据，应用于整个页面。

- 如果设置了 `http-equiv` 属性，meta 元素则是编译指令，提供的信息与类似命名的 HTTP 头部相同。

- 如果设置了 `charset` 属性，meta 元素是一个字符集声明，告诉文档使用哪种字符编码。

- 如果设置了 `itemprop` 属性，meta 元素提供用户定义的元数据。

## 1. `charset` 属性

这个属性声明了文档的字符编码。如果使用了这个属性，其值必须是与 ASCII 大小写无关的 `utf-8`。

```html
<meta charset="utf-8">
```

## 2. `content` 属性

此属性包含 `http-equiv` 或 `name` 属性的值，具体取决于所使用的值。

## 3. `http-equiv` 属性

属性定义了一个编译指示指令，与 `content` 一起使用。

这个属性叫做 `http-equiv(alent)` 是因为所有允许的值都是特定 HTTP 头部的名称，如下：

- `content-security-policy`
  它允许页面作者定义当前页的内容策略。 内容策略主要指定允许的服务器源和脚本端点，这有助于防止跨站点脚本攻击。

- `content-type`
  如果使用这个属性，其值必须是"text/html; charset=utf-8"。
  注意：该属性只能用于 MIME type 为 text/html 的文档，不能用于 MIME 类型为 XML 的文档。

- `default-style`
  设置默认 CSS 样式表组的名称。

- `x-ua-compatible`
  如果指定，则 content 属性必须具有值 "IE=edge"。用户代理必须忽略此指示。
  
- `refresh`
  这个值指定：
  - 如果 content 只包含一个正整数，则为重新载入页面的时间间隔(秒)；
  - 如果 content 包含一个正整数，并且后面跟着字符串 ';url=' 和一个合法的 URL，则是重定向到指定链接的时间间隔(秒)。 
    
```html
<meta http-equiv="refresh" content="3;url=https://www.mozilla.org">
```

## 4. name 属性

name 和 content 属性可以一起使用，以名-值对的方式给文档提供元数据，
其中 name 作为元数据的名称，content 作为元数据的值。

`name` 的值可参考：[HTML的标准元数据名称](081-HTML的标准元数据名称.md)
