# HTML 全局属性

全局属性是所有 HTML 元素共有的属性; 它们可以用于所有元素，部分属性可能对某些元素不起作用。

## 1. accesskey 属性(不推荐使用)

提供了为当前元素生成快捷键的方式。属性值必须包含一个可打印字符，不区分大小写。

激活 `accesskey` 的操作取决于浏览器及其平台。

```html
<button accesskey="B" onclick="onClick()">点击</button>

<script>
  const onClick = function () {
    console.log("hello");
  };
</script>
```

### 1.1 (window / Linux) + Firefox

```shell
Alt + Shift + key
```

### 1.2 window + (Internet Explorer / Chrome / Safari / Opera 15+)

```shell
Alt + key
```

### 1.3 Mac + (Chrome / Safari / Opera 15+)

```shell
Control + Alt + key
```

### 1.4 Mac + Firefox

```shell
# Firefox 57 +
Control + Option + key
Control + Alt + key

# Firefox 14 +
Control + Alt + key

# Firefox 13 +
Control + key
```

## 2. autocapitalize 属性

控制用户输入/编辑文本输入时文本输入是否自动大写，以及如何自动大写。属性必须取下列值之一：

- `off` or `none`: 没有应用自动大写（所有字母都默认为小写字母）。

- `on` or `sentences`: 每个句子的第一个字母默认为大写字母；所有其他字母都默认为小写字母。

- `words`: 每个单词的第一个字母默认为大写字母；所有其他字母都默认为小写字母。

- `characters`: 所有的字母都默认为大写。

**注意**：`autocapitalize` 不会应用于 `<input>` 并且 type 属性 值为 `url`、`email`、`password`
启用自动大写。

## 3. class 属性

一个以空格分隔的元素的类名（classes ）列表，允许 CSS 和 Javascript 通过类选择器 (class selectors) 或 DOM 方法。

class 的命名没有要求，但最好使用可以表达元素语义目的的名称。

## 4. contenteditable 属性

表示元素是否可被用户编辑，即用户可直接在网页上对可编辑的元素进行修改。

值为布尔类型。

```css
/* css 可以修改编辑处光标的颜色 */
[contenteditable="true"] {
  caret-color: red;
}
```

## 5. contextmenu 属性（已过时）

## 6. data-\* 属性

可在 HTML 元素中存储额外的信息，并且 JavaScript 和 CSS 均可访问。

**注意**：`*` 不能以 `xml` 开头，不能包含大写字母，不能包含任何分号。

```html
<article
  id="electriccars"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars"
>
  ...
</article>

<style>
  article[data-columns="3"] {
    width: 400px;
  }

  article[data-columns="4"] {
    width: 600px;
  }
</style>

<script>
  const article = document.querySelector("#electriccars");

  article.dataset.columns; // "3"
  article.dataset.indexNumber; // "12314"
  article.dataset.parent; // "cars"
</script>
```

## 7. dir 属性

指示元素中文本方向的枚举属性，取值如下：

- `ltr`, 指从左到右，用于那种从左向右书写的语言（比如英语）；

- `rtl` 指从右到左，用于那种从右向左书写的语言（比如阿拉伯语）；

- `auto` 指由用户代理决定方向。

## 8. draggable 属性

指示是否可以 使用 Drag and Drop API 拖动元素，布尔值，true 表示可被拖动，false 不可拖动。

## 9. dropzone 属性

表示什么内容类型可以拖放到元素上。

- `copy`，它表明拖放行为会创建被拖放元素的副本。

- `move`，它表明被拖放元素会移动到新的位置。

- `link`，它会创建被拖放数据的链接。

## 10. hidden 属性

布尔值，一个元素设置了这个属性，它就不会被显示，且不占据空间。

该属性会被 CSS 的 `display` 属性覆盖。

## 11. id 属性

定义了一个全文档唯一的标识符 (ID)，可用于在链接（锚点）、脚本和样式（通过 CSS）中辨识元素。

`id` 的值不得包含空白字符（whitespace，包括空格和制表符等）

## 12. lang 属性

帮助定义元素的语言。

```html
<p lang="en-GB">This paragraph is defined as British English.</p>
```

## 13. part 属性

包含一个以元素中 part 属性名称组成的列表，该列表以空格分隔。
通过 Part 的名称，可以使用 CSS 伪元素“::part”来选择 shadow 树中指定元素并设置其样式 。

## 14. slot 属性

将一个 shadow DOM shadow 树中的槽分配给一个元素： 带有 slot 属性的元素分配给由 <slot> 创建的槽，它的 name 属性的值匹配 slot 属性的值。

## 15. spellcheck 属性

枚举属性，定义是否可以检查元素的拼写错误，即值需要是 true 或 false（注意不是布尔值）。

## 16. style 属性

CSS 样式，建议在单独文件中定义样式。

## 17. tabindex 属性

指示其元素是否可以聚焦，以及它是否/在何处参与顺序键盘导航。

默认值是 0，最大值不应该超过 32767。

该属性接受一个整数作为值，具体如下：

- tabindex=负值，表示元素可聚焦，但是不能通过键盘导航访问到，用 JS 做 页面小组件内部导航比较有用。

- tabindex=0，表示元素可聚焦，且可通过键盘导航聚焦到该元素，顺序由处于的 DOM 结构决定。

- tabindex=正值，表示可聚焦，并且可通过键盘导航聚焦到该元素；值越大，聚焦到顺序越靠后。如果值相同，则由 DOM 顺序决定。

## 18. title 属性

包含表示与其所属元素相关信息的文本。 这些信息通常可以作为提示呈现给用户,但不是必须的。

title 属性可以包含多行。每个插入的 U+000A LINE FEED (LF) 代表一个换行。

```html
<p>
  Newlines in title should be taken into account,like this
  <abbr title="This is a multiline title">example</abbr>.
</p>
```

## 19. translate 属性

用来规定对应元素的属性值及其子文本节点内容，是否跟随系统语言作出对应的翻译变化。

- `yes` 或者不设置值，表示网页进行本地化的时候，跟随翻译。

- `no` 表示无需翻译。
