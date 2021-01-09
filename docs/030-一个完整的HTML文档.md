# 完整 HTML 文档解析

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>我的测试站点</title>
  </head>
  <body>
    <p>这是我的页面</p>
  </body>
</html>
```

## 1. `<!DOCTYPE html>`

声明文档类型，该声明指示浏览器使用哪个 `HTML` 版本进行解析文档，且必须位于第一行，位于 `<html>` 标签之前，大小写不敏感。

常用的 DOCTYPE 声明如下：

### 1.1 HTML 5

```html
<!DOCTYPE html>
```

### 1.2 HTML 4.01 Strict

该 DTD 包含所有 HTML 元素和属性，但不包括展示性的和弃用的元素（比如 font）。不允许框架集（Framesets）。

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

### 1.3 HTML 4.01 Transitional

该 DTD 包含所有 HTML 元素和属性，但不包括展示性的和弃用的元素（比如 font）。不允许框架集（Framesets）。

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" 
"http://www.w3.org/TR/html4/loose.dtd">
```

### 1.4 HTML 4.01 Frameset

该 DTD 等同于 HTML 4.01 Transitional，但允许框架集内容。

```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" 
"http://www.w3.org/TR/html4/frameset.dtd">
```

## 2. `<html>`

包裹了整个完整的页面，是页面的根元素。

## 3. `<head>`

这个元素是一个容器，包含了所有想包在 HTML 页面但是不想在 HTML 页面显示的内容。这些内容包括想在搜索结果中出现的关键字
和页面描述，CSS 样式，字符集声明等等。

## 4. `<meta charset="utf-8">`

这个元素设置文档使用 utf-8 字符集编码，utf-8 字符集包含了人类大部分的文字。设置字符集基本是必须的，可以避免出现很多问题。

## 5. `<title>`

设置页面的标题，该标题也会在上下文中被使用，比如用户的历史、书签或搜索的结果中。

## 6. `<body>`

包含了访问页面时，所有显示在页面中的内容，文本、图片、音频、游戏等等。
