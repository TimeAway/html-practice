# HTML 元数据 - `<style>`

HTML 的 `<style>` 元素包含文档的样式信息或者文档的部分内容。默认情况下，该标签的样式信息通常是 CSS 的格式。

## 1. type 属性

该属性以 `MIME` 类型定义样式语言。如果未指定，则默认为 `text/css`。

## 2. media 属性

该属性规定该样式适用于哪个媒体，即设备的类别。值可取 `all`、`print`、`screen`、`speech`，默认 `all`。

## 3. nonce 属性

一种加密的随机数（一次使用的数字），用于在style-src Content-Security-Policy中将内联样式列入白名单。 

服务器每次发送策略时都必须生成一个唯一的随机数值。 提供一个无法猜测的随机数非常重要，因为绕开资源策略是微不足道的。

## 4. title 属性

指定可选的样式表。

## 例 1. 简单的样式表

```html
<!doctype html>
<html>
<head>
  <style>
    p {
      color: red;
    }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```

## 例 2. 包含媒体选择

下面样式表示视图宽度在小于 500px 时生效

```html
<!doctype html>
<html>
<head>
  <style media="all and (max-width: 500px)">
    p {
      color: blue;
      background-color: yellow;
    }
  </style>
</head>
<body>
  <p>This is my paragraph.</p>
</body>
</html>
```
