# HTML 标签# HTML 标签

主要针对一些带有属性（非全局属性）的标签的介绍

## 1. `hr` 标签

表示段落级元素之间的主题转换（例如，一个故事中的场景的改变，或一个章节的主题的改变）。

该元素语义上在浏览器中标签为一个水平线，但是如果需要水平线，使用 CSS 样式修饰。

### 1.1 `align` 属性：对齐方式，默认 left

### 1.2 `color` 属性： 颜色名或十六进制设置颜色

### 1.3 `noshade` 属性： 去除阴影

### 1.4 `size` 属性：使用像素设置高度

### 1.5 `width` 属性：使用像素或百分比设置宽度

## 2. `ol` 标签

有序列表，通常渲染为一个带有编号的列表。

### 2.1 `reversed` 属性：布尔值，指定列表中的条目是否是倒序排列。

### 2.2 `start` 属性：整数值，指定了列表的起始值。

### 2.3 `type` 属性：设置编号的类型

- `a` 表示小写英文字母编号
- `A` 表示大写英文字母编号

- `i` 表示小写罗马数字编号

- `I` 表示大写罗马数字编号

- `1` 表示数字编号（默认）

## 3. `li` 标签

用于列表里面的条目。必须包含一个父元素：有序列表 `ol`、无序列表 `ul`、菜单 `menu`。在无序列表
或菜单表现为点排列，在有序列表里面表现为升序的数字或字母。

### 3.1 `value` 属性：有序列表中的序号，只能使用数字

## 4. `pre` 元素

表示预定义格式文本。
在该元素中的文本通常按照原文件中的编排，以等宽字体的形式展现出来，文本中的空白符（比如空格和换行符）都会显示出来。

---

## 5. `a` 标签

可以创建通向其他网页、文件、同一页面内的位置、电子邮件地址或任何其他 URL 的超链接。

### 5.1 `download` 属性

此属性指示浏览器下载 URL 而不是导航到它，因此将提示用户将其保存为本地文件。

如果属性有一个值，那么此值将在下载保存过程中作为预填充的文件名。

**注意**：该属性仅适用于同源属性，如果 HTTP 头中的 `Content-Disposition` 属性赋予了一个不同于此属性的文件名，
HTTP 头属性优先于此属性。

### 5.2 `href` 属性

超链接指向的 URL 或 URL 片段。

- URL 片段是哈希标记（#）前面的名称，哈希标记指定当前文档中的内部目标位置（HTML 元素的 ID）。

- 使用 href="#top" 或者 href="#" 链接返回到页面顶部。

- URL 不限于基于 Web（HTTP）的文档，例如，在大多数浏览器中正常工作的 `file:`、`ftp:` 和 `mailto：`。

### 5.3 `hreflang` 属性

该属性用于指定链接文档的人类语言，其仅提供建议。

### 5.4 `ping` 属性

包含一个以空格分隔的 url 列表，当跟随超链接时，将由浏览器(在后台)发送带有正文 PING 的 POST 请求。通常用于跟踪。

### 5.5 `referrerpolicy`属性

表明在获取 URL 时发送哪个提交者（referrer）:

- `no-referrer` 表示 `Referer`: 头将不会被发送。

- `no-referrer-when-downgrade` 表示当从使用 HTTPS 的页面导航到不使用 TLS(HTTPS)的来源 时不会发送 Referer: 头。
  如果没有指定策略，这将是用户代理的默认行为。

- `origin` 表示 `referrer` 将会是页面的来源，大致为这样的组合：主机和端口（不包含具体的路径和参数的信息）。

- `origin-when-cross-origin` 表示导航到其它源将会限制为这种组合：主机 + 端口，而导航到相同的源将会只包含 referrer 的路径。

- `strict-origin-when-cross-origin`

- `unsafe-url` 表示 `referrer` 将会包含源和路径（domain + path）（但是不包含密码或用户名的片段）。
  这种情况是不安全的，因为它可能会将安全的 URLs 数据泄露给不安全的源。

### 5.6 `rel` 属性

指定了目标对象到链接对象的关系。

### 5.7 `target` 属性

该属性指定在何处显示链接的资源。

- `_self`: 当前页面加载。默认值。

- `_blank`: 新窗口打开。

- `_parent`: 加载响应到当前框架的父框架。如果没有上级框架，则与 `_self` 行为相同。

- `_top`: 加载的响应成完整的，原来的窗口，取消所有其它 frame。如果没有上级框架，则与 `_self` 行为相同。

### 5.8 `type` 属性

指定在一个 MIME type 链接目标的形式的媒体类型。其仅提供建议。

## 6. `q` 标签

表示一个封闭的并且是短的行内引用的文本。 这个标签是用来引用短的文本。

对于长的文本的引用请使用 `blockquote` 替代.

### 6.1 `cite` 属性

这个属性的值是 URL，意在指出被引用的文本的源文档或者源信息。

```html
<p>
  Everytime Kenny is killed, Stan will announce
  <q cite="http://en.wikipedia.org/wiki/Kenny_McCormick#Cultural_impact">
    Oh my God, you/they killed Kenny! </q
  >.
</p>
```

## 7. `time` 标签

用来表示 24 小时制时间或者公历日期，若表示日期则也可包含时间和时区。

此元素意在以机器可读的格式表示日期和时间。

### 7.1 `datetime` 属性

该属性表示此元素的时间和日期，并且属性值必须是一个有效的日期格式，并可包含时间。

## 8. `map` `area` 标签

这两个属性一起使用来定义一个图像映射(一个可点击的链接区域).

### 8.1 `name` 属性 - `map`

name 属性 给 map 一个名字用来查询，这个属性是必须的，值必须不能为空并且不能带空格。
name 属性不准与同文档中其他 map 元素的值相同，如果 id 属性也被添加，name 属性和 id 属性的值必须相同。

### 8.2 `alt` 属性

在未显示图像的浏览器上显示代替的文本字符串。

### 8.3 `coords` 属性

给热点区域设定具体的坐标值。这个值的数值和意义取决于这个值所描述的形状属性。

- 对于矩形或长方形, 这个 coords 值为两个 X,Y 对：左上、右下。
- 对于圆形, 这个值是 x,y,r ，这里的 x,y 是一对确定圆的中心的坐标而 r 则表示的是半径值。

- 对于多边和多边形，这个值是用 x,y 对表示的多边形的每一个点：x1,y1,x2,y2,x3,y3,等等。

HTML4 里, 值可能是像素数量或者百分比, 区别是不是有%出现; HTML5 里, 只可能是像素的数量.

### 8.4 `download` 属性

这个属性如果存在的话, 表明作者想把超链接用于下载一个资源。同标签 `a`。

### 8.5 `href` 属性

area 的超链接, 值为一个 URL.

### 8.6 `hreflang` 属性

指明链接资源的语言类型。

### 8.7 `media` 属性

指明链接资源的媒体类型，例：print and screen。如果此属性省略，默认全部。

### 8.8 `rel` 属性

对于包含 href 属性的锚，该属性指定目标对象与链接对象的关系。该值是一个逗号分隔的链接类型值列表。

### 8.9 `shape` 属性

相关联的热点的形状。

### 8.10 `target` 属性

同 `a` 标签的 `target`。

### 8.11 `type` 属性

该属性指定了用于链接目标的 MIME 类型的媒体类型。

```html
<map name="primary">
  <area shape="circle" coords="200,250,25" href="another.htm" />
  <area shape="default" />
</map>
```

## 9. `img` 标签

表示将一份图像嵌入文档。支持的图像格式如下：

| 编写 | 文件格式             | MIME 类型     | 文件拓展名                       |
| ---- | -------------------- | ------------- | -------------------------------- |
| APNG | 动态便携式网络图像   | image/apng    | .apng                            |
| BMP  | 位图文件             | image/bmp     | .bmp                             |
| GIF  | 图像互换格式         | image/gif     | .gif                             |
| ICO  | 微软图标             | image/x-icon  | .ico, .cur                       |
| BMP  | 位图文件             | image/bmp     | .bmp                             |
| JPEG | 联合影像专家小组图像 | image/jpeg    | .jpg, .jpeg, .jfif, .pjpeg, .pjp |
| PNG  | 便携式网络图像       | image/png     | .png                             |
| SVG  | 可缩放矢量图形       | image/svg+xml | .svg                             |
| TIFF | 标签图像文件格式     | image/tiff    | .tif, .tiff                      |
| WebP | 万维网图像格式       | image/webp    | .webp                            |

### 9.1 `alt` 属性

图像的备用文本描述。

### 9.2 `crossorigin` 属性

是否必须使用 CORS 完成相关图像的抓取。
启用 CORS 的图像 可以在 `<canvas>` 元素中重复使用，而不会被污染（tainted）。

- `anonymous` 执行一个跨域请求，但是没有发送证书。

- `use-credentials` 一个有证书的跨域请求发送。

### 9.2 `decoding` 属性

为浏览器提供图像解码方式上的提示。

- `sync` 同步解码图像，实现与其他内容的显示相互斥的原子显示。

- `async` 异步解码图像，以减少其他内容的显示延迟。

- `auto` 默认值：不指定解码方式，由浏览器决定哪一种对于用户来说是最合适的。

### 9.3 `width`、`height` 属性

图像的宽度和高度，单位像素，如果只指定某一个，浏览器会自动缩放。

### 9.4 `importance` 属性

指示下载资源时相对重要性，或者说优先级。

- `auto` 不指定优先级。浏览器可以使用自己的算法来为图像选择优先级。

- `high` 此图像在下载时优先级较高。

- `low` 此图像在下载时优先级较低。

### 9.5 `intrinsicsize` 属性（不支持）

告诉浏览器忽略图像本身的宽高。

### 9.6 `ismap` 属性

这个布尔属性表示图像是否是服务器端 map 的一部分。如果是，那么点击图片的精准坐标将会被发送到服务器。

### 9.7 `loading` 属性

指示浏览器应当如何加载该图像。

- `eager` 立即加载图像，不管它是否在可视视口（visible viewport）之外（默认值）。

- `lazy` 延迟加载图像，直到它和视口接近到一个计算得到的距离，由浏览器定义。

### 9.8 `referrerpolicy` 属性

指示在获取资源时使用哪个引用。

### 9.9 `sizes` 属性

表示资源大小的、以逗号隔开的一个或多个字符串。每一个资源大小包括：一个媒体条件，一个资源尺寸的值。

当 `srcset` 中的资源使用了宽度描述符 w 时，用户代理会使用当前图像大小来选择 `srcset` 中合适的一个图像 URL。

如果没有设置 `srcset` 属性，或者没有属性值，那么 `sizes` 属性也将不起作用。

### 9.10 `srcset` 属性

以逗号分隔的一个或多个字符串列表表明一系列用户代理使用的可能的图像。

每一个字符串由以下组成： 一个是指向图像的 URL，另一个是可选的，该值可以是一个宽度描述符，
这是一个正整数，后面紧跟 'w' 符号。该整数宽度除以 sizes 属性给出的资源（source）大小来计算得到有效的像素密度，
即换算成和 x 描述符等价的值。或者是一个像素密度描述符，这是一个正浮点数，后面紧跟 'x' 符号。

如果没有指定源描述符，那它会被指定为默认的 1x。

```html
<!-- 如下 srcset 属性，它引用了 MDN 标志高清版本；在高分辨率设备上，将被优先加载，取代 src 属性中的图像。 -->
<img
  src="https://developer.mozilla.org/static/img/favicon72.png"
  alt="MDN logo"
  srcset="https://developer.mozilla.org/static/img/favicon144.png 2x"
/>
```

```html
<!-- 当匹配了媒体条件 (min-width: 600px) 时，图像将宽 200px，否则宽 50vw（视图宽度的50%） -->
<img
  src="/files/16864/clock-demo-200px.png"
  alt="Clock"
  srcset="
    /files/16864/clock-demo-200px.png 200w,
    /files/16797/clock-demo-400px.png 400w
  "
  sizes="(max-width: 600px) 200px, 50vw"
/>
```

### 9.11 `src` 属性

图像的 URL，这个属性对 `<img>` 元素来说是必需的。
在支持 `srcset` 的浏览器中，`src` 被当做拥有一个像素密度的描述符 1x 的候选图像处理，
除非一个图像拥有这个像素密度描述符已经被在 `srcset` 或者 `srcset` 包含 w 描述符中定义了。

### 9.12 `usemap` 属性

与元素相关联的 image map 的部分 URL（以 '#' 开始的部分）。

如果 `<img>` 元素是 `<a> `或 `<button>` 元素的后代元素则不能使用这个属性。

## 10. `audio`、`video`、`track` `source` 标签

[audio 音频](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio)

[video 视频](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/video)

[track 字幕](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/audio)

[source 媒体资源](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/source)

## 11. `object` 标签

表示引入一个外部资源，这个资源可能是一张图片，一个嵌入的浏览上下文，亦或是一个插件所使用的资源。

### 11.1 `data` 属性

一个合法的 URL 作为资源的地址，，需要为 data 和 type 中至少一个设置值。

### 11.2 `form` 属性

对象元素关联的 form 元素（属于的 form）。 取值必须是同一文档下的一个 `<form>` 元素的 ID。

### 11.3 `width`、`height` 属性

资源显示的宽度和高度，单位是 CSS 像素。

### 11.4 `name` 属性

浏览上下文名称（HTML5），或者控件名称（HTML 4）。

### 11.5 `type` 属性

`data` 指定的资源的 MIME 类型，需要为 `data` 和 `type` 中至少一个设置值。

### 11.6 `usemap` 属性

指向一个 `<map>` 元素的 hash-name；格式为 ‘#’ 加 map 元素 name 元素的值。

```html
<object
  type="application/pdf"
  data="/media/examples/In-CC0.pdf"
  width="250"
  height="200"
></object>
```

## 12. `params` 标签

为 `object` 标签定义参数。

### 12.1 `name` 属性

参数的名称。

### 12.2 `type` 属性

仅当 `valuetype` 设置为“ref”时才使用。根据 URI 中给定的数据确定 MIME 类型。

### 12.3 `value` 属性

参数的值。

### 12.4 `valuetype` 属性

确定参数的类型。可选值如下：

- data: 默认值。该值作为字符串变量传递给对象实例。

- ref: 该值是存储运行时变量的资源的 URI。

- object: 同一页面（document）中另一个 `<object>` 的 ID。
