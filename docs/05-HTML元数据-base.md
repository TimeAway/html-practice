# HTML 元数据 - `<base>`

`<base>` 元素用于指定一个文档中包含的所有 URL 的根 URL，且只能有一个 `<base>` 元素，如果
有多个 `base`，则只会使用第一个，其余会被忽略。

该 `<base>` 设置的 URL，可以通过 JS 脚本 `document.baseURI` 查询。如果文档不包含 `<base>`
元素，则默认为 `document.location.href`

## 1. `href` 属性

用于文档中相对 URL 地址的基础 URL。允许绝对值和相对值。

## 2. `target` 属性

默认浏览上下文的关键字，如果链接没有指定此属性，则会使用该属性值。

- _self: 载入结果到当前浏览上下文中。（该值是元素的默认值）。

- _blank: 载入结果到一个新的未命名的浏览上下文。

- _parent: 载入结果到父级浏览上下文（如果当前页是内联框）。如果没有父级结构，该选项的行为和_self一样。

- _top: 载入结果到顶级浏览上下文（该浏览上下文是当前上下文的最顶级上下文）。如果没有父级，该选项的行为和_self一样。

## 使用说明

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>This is an example for the &lt;base&gt; element</title>
    <base href="https://www.example.com/news/index.html" target="_blank" />
    <!-- 无效 -->
    <base target="_blank">
    <base target="_top" href="http://www.example.com/">
  </head>
  <body>
    <p>Visit the <a href="archives.html">archives</a>.</p>
  </body>
</html>

<!-- 上面 a 链接的实际地址是 https://www.example.com/news/archives.html -->
```
