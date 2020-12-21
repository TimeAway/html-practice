# HTML 内容分区元素

内容分区元素允许将文档内容从逻辑上进行组织划分。

使用包括页眉(header)、页脚(footer)、导航(nav)和标题(h1~h6)等分区元素，来为页面内容创建明确的大纲，
以便区分各个章节的内容。

## 1. `address` 元素

表示其中的 HTML 提供了某个人或某个组织等的联系信息，可以使真实地址、URL、电子邮箱、电话号码、
社交媒体账号、地理坐标等等。

**使用说明**

如果一个和联系信息无关的地址等，应改用 `<p>` 标签，`address` 通常放在 `<footer>` 元素中。

```html
<address>
  <a href="mailto:jim@rock.com">jim@rock.com</a><br />
  <a href="tel:+13115552368">(311) 555-2368</a>
</address>
```

## 2. `article` 元素

表示文档、页面、应用或网站中的独立结构，其意在成为可独立分配的或可复用的结构，如在发布中，
它可能是论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。

**使用说明**

- 每个 `<article>` ，通常包含标题元素作为其子元素。

- 当 `<article>` 元素嵌套使用时，则该元素代表与外层元素有关的文章。
  例如，代表博客评论的 `<article>` 元素可嵌套在代表博客文章的 `<article>` 元素中。

- `<article>` 元素的作者信息可通过 `<address>` 元素提供，但是不适用于嵌套的 `<article>` 元素。

```html
<article class="forecast">
  <h1>Weather forecast for Seattle</h1>
  <article class="day-forecast">
    <h2>03 March 2018</h2>
    <p>Rain.</p>
  </article>
</article>
```

## 3. `aside` 元素

表示一个和其余页面内容几乎无关的部分，被认为是独立于该内容的一部分并且可以被单独的拆分出来而不会使整体受影响。
其通常表现为侧边栏或者标注框。

## 4. `footer` 元素

表示最近一个章节内容或者根节点（sectioning root ）元素的页脚。
一个页脚通常包含该章节作者、版权数据或者与文档相关的链接等信息。

## 5. `header` 元素

展示介绍性内容，通常包含一组介绍性的或是辅助导航的实用元素。
它可能包含一些标题元素，但也可能包含其他元素，比如 Logo、搜索框、作者名称，等等。

## 6. `hgroup` 元素

表示文档章节所属的多级别的目录，它将多个 `<h1>` 至 `<h6>` 的子元素组装到一起。

```html
<hgroup>
    <h1>Calculus I</h1>
    <h2>Fundamentals</h2>
</hgroup>
```

## 7. `main` 元素

呈现了文档的 <body> 或应用的主体部分。 主体部分由与文档直接相关，或者扩展于文档的中心主题、应用的主要功能部分的内容组成。

在文档中，<main> 元素的内容应当是独一无二的。任何同时存在于任意一系列文档中的相同、重复内容，
比如侧边栏、导航栏链接、版权信息、网站 Logo，搜索框（除非搜索框为文档的主要功能），都不应当被包含在其内。

```html
<main>
  <h1>Apples</h1>
  <p>The apple is the pomaceous fruit of the apple tree.</p>

  <article>
    <h2>Red Delicious</h2>
    <p>These bright red apples are the most common found in many
    supermarkets.</p>
    <p>... </p>
    <p>... </p>
  </article>
</main>
```

## 8. `nav` 元素

表示页面的一部分，其目的是在当前文档或其他文档中提供导航链接。导航部分的常见示例是菜单，目录和索引。

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">About</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

## 9. `section` 元素

表示一个包含在HTML文档中的独立部分，它没有更具体的语义元素来表示，一般来说会有包含一个标题。

```html
<section>
  <h1>Heading</h1>
  <p>Bunch of awesome content</p>
</section>
```
