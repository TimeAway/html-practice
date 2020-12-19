# HTML 的元数据

元数据是设置其余内容的呈现或行为，设置文档与其他文档的关系，传递其他带外信息的内容。

元数据主要包括：`head`、`base`、`link`、`meta`、`noscript`、`script`、`style`、`template`
、`title`

## 1. head 元素

`head` 元素是 `html` 元素的第一个元素，表示 `Document` 元数据的集合。

## 2. title 元素

`title` 表示文档的标题或名称。该标题也会在上下文中被使用，比如用户的历史、书签或搜索的结果中

通过 `document.title[=value]` 获取或设置文档的标题。

## 3. base 元素

`base` 元素用于解析 URL 的文档基础 URL，以及跟随超链接的默认浏览上下文的名称。

每个文档最多包含一个 `base`，如果有多个，则会忽略除第一个外的其他的。

`base` 包含两个属性，分别是：

- href，设置基础链接

- target，表示超链接是如何打开的，值包括 `_blank`、`_self`、`_parent`、`_top`
  ，如果文档中的超链接也指定了该属性，则会覆盖此属性

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>This is an example for the &lt;base&gt; element</title>
    <base href="https://www.example.com/news/index.html" target="_blank" />
    <!-- 无效 -->
    <base href="https://www.baidu.com/news/index.html" />
  </head>
  <body>
    <p>Visit the <a href="archives.html">archives</a>.</p>
  </body>
</html>

<!-- 上面 a 链接的实际地址是 https://www.example.com/news/archives.html -->
```

## 4. link 元素

`link` 可以让文档链接到其他资源，常用于引入 `css` 样式。

除全局属性外，`link` 包含如下属性：

### 4.1 href 属性

表示链接资源的地址。

### 4.2 media 属性

指定了该资源适用哪种媒体，且必须是合法的 [媒体查询列表](https://whatwg-cn.github.io/html/#valid-media-query-list)

### 4.3 nonce 属性

一个加密随机数 （"一次性数字"）用于 Content Security Policy 来确定 该链接指定的外部资源是否会被加载和应用于该文档。它的值是文本。

### 4.4 type 属性

给出了被链接资源的 [MIME](https://mimesniff.spec.whatwg.org/#mime-type) 类型。它纯属建议性的，但必须是合法的 MIME 类型。
对于外部资源链接， type 属性用于提示用户代理避免获取它们不支持的资源。

### 4.5 title 属性

给出了链接的标题。link 元素上的 title 属性 与多数其他元素的全局 title 属性不同，没有标题的链接不继承父元素的标题：它只是没有标题。

### 4.6 imagesrcset、imagesizes 属性

`imagesrcset` 和 `imagesizes` 属性只能用于 `rel` 属性指定了 `preload` 关键字，且 as 属性在处于 "image" 状态的 link 元素上。

其表示预先加载页面中的图片资源，即如果页面中存在多个图片，首先加载 link 中适应屏幕宽度的图片，其后再加载其他图片。

如果指定了 `imagesizes` 属性，页面会匹配到该宽度下的图片。

这两个属性用法上等同于 `<img>` 标签的 `srcset` 和 `sizes` 属性。根据当前屏幕宽度选择性的加载相应的图片，而不是固定的图片。

```html
<!-- 如下会预加载适当的资源，后续会被 img 使用 -->
<link
  rel="preload"
  as="image"
  imagesrcset="wolf_400px.jpg 400w, wolf_800px.jpg 800w, wolf_1600px.jpg 1600w"
  imagesizes="50vw"
/>

<!-- ... later, or perhaps inserted dynamically ... -->
<img
  src="wolf.jpg"
  alt="A rad wolf"
  srcset="wolf_400px.jpg 400w, wolf_800px.jpg 800w, wolf_1600px.jpg 1600w"
  sizes="50vw"
/>
```

```html
<!-- imagesrcset 属性可以和 media 属性一起使用来预加载适当的资源 picture 元素选择的资源 -->
<link
  rel="preload"
  as="image"
  imagesrcset="dog-cropped-1x.jpg, dog-cropped-2x.jpg 2x"
  media="(max-width: 800px)"
/>
<link
  rel="preload"
  as="image"
  imagesrcset="dog-wide-1x.jpg, dog-wide-2x.jpg 2x"
  media="(min-width: 801px)"
/>

<!-- ... later, or perhaps inserted dynamically ... -->
<picture>
  <source
    srcset="dog-cropped-1x.jpg, dog-cropped-2x.jpg 2x"
    media="(max-width: 800px)"
  />
  <img src="dog-wide-1x.jpg" srcset="dog-wide-2x.jpg 2x" alt="An awesome dog" />
</picture>
```

**扩展阅读：**[内容预加载](05-通过rel=%22preload%22进行内容预加载.md)

### 4.7 as 属性

`as` 属性为 `href` 指定的资源的预加载请求指定了可能的地址，它是一个枚举属性，可取的值包括 `script`、`style`、`image`、
`video`、`audio`、`track`、`font`、`fetch`、。

该属性必须指定在 rel 属性包含 preload 关键字的 link 元素上。也可以指定在 rel 属性包含 modulepreload 关键字的 link 元素上；
这种情况下它的值必须是 script-like 地址。 其他 link 元素不能使用这个属性。'

### 4.8 disabled 属性

`diabled` 属性是一个布尔值，只能用在 `rel` 属性包含 `stylesheet` 关键字的 link 元素上，表示该样式不会被加载。

如下可动态的移除 `disabled` 属性，获取对应的样式。

```html
<link disabled rel="alternate stylesheet" href="css/pooh" />

<script>
  document.querySelector("link").removeAttribute("disabled");
</script>
```

### 4.9 rel 属性

表示当前文档与目标资源之间的关系。

包括 `alternate`， `dns-prefetch`， `icon`， `modulepreload`, `next`， `pingback`， `preconnect`， `prefetch`，
`preload`， `prerender`， `search`，和 `stylesheet`。

## 5. meta 元素

<meta> 元素 表示 很多不能用 title，base，link，style， 和 script 元素表达的元数据。

<meta> 包含四个属性：name，http-equiv，charset，和 itemprop，必须是其中之一。

如果指定了 name，http-equiv， 或 itemprop，那么必须也指定 content 属性。

<meta> 元素上 charset 属性 对 XML 文档不起作用。

### 5.1 name 属性

如果设置了 name 属性，meta 元素提供的是文档级别（document-level）的元数据，应用于整个页面。

name 和 content 属性可以一起使用，以名-值对的方式给文档提供元数据，其中 name 作为元数据的名称，content 作为元数据的值。
