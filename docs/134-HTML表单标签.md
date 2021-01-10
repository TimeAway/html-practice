# HTMl 表单元素

## 1. `<form>` 元素

表示文档中的一个区域，此区域包含交互控件，用于向 Web 服务器提交信息。

### 1.1 `accept-charset` 属性

一个空格分隔或逗号分隔的列表(HTML5 只允许空格)，此列表包括了服务器支持的字符编码。

### 1.2 `autocomplete` 属性

用于指示 input 元素是否能够拥有一个默认值，此默认值是由浏览器自动补全的。

此设定可以被属于此表单的子元素的 autocomplete 属性覆盖。可能的值包括 `off` `on`

### 1.3 `name` 属性

表单的名称。HTML 4 中不推荐（应使用 id）。在 HTML 5 中，该值必须是所有表单中独一无二的，而且不能是空字符串。

### 1.4 `rel` 属性

根据 value 创建一个超链接。

### 1.5 `action` 属性

处理表单提交的 URL。

这个值可被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素上的 `formaction` 属性覆盖。

### 1.6 `enctype` 属性

- `application/x-www-form-urlencoded`: 未指定时的默认值。

- `multipart/form-data`: 如果使用 type 属性的 `<input>` 元素设置文件类型，使用此值。

- `text/plain`

这个值可被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素上的 `formenctype` 属性覆盖。

### 1.7 `method` 属性

- `post`：指的是 HTTP POST 方法；表单数据会包含在表单体内然后发送给服务器.
- `get`：指的是 HTTP GET 方法；表单数据会附加在 action 属性的 URL 中，并以 '?' 作为分隔符，没有副作用 时使用这个方法。
- `dialog`：如果表单在 `<dialog>` 元素中，提交时关闭对话框。

这个值可被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素上的 `formmethod` 属性覆盖。

### 1.8 `novalidate` 属性

此布尔值属性表示提交表单时不需要验证表单。 如果没有声明该属性 （因此表单需要通过验证）。

这个值可被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素上的 `formnovalidate` 属性覆盖。

### 1.9 `target` 属性

此属性指定一个名称或关键字，表示接收提交的表单后在哪里显示响应。

这是一个浏览上下文（例如 tab，window 或内联框架）的名称或关键字。如果指定了，它会重写 button 拥有者的 target 属性。

- `_self`: 在同一个浏览上下文中加载响应作为当前的。未指定时此值为默认值。

- `_blank`: 在一个新的不知名浏览上下文中加载响应。

- `_parent`: 在当前浏览上下文父级中加载响应。如果没有父级的，此选项将按 \_self 执行。

- `_top`: 在顶级浏览上下文（即当前浏览上下文的祖先，且没有父级）中架加载响应。如果没有顶级的，此选项将按\_self 执行

这个值可被 `<button>`、`<input type="submit">` 或 `<input type="image">` 元素上的 `formtarget` 属性覆盖。

## 2. `<button>` 元素

表示一个可点击的按钮，可以用在表单或文档其它需要使用简单标准按钮的地方。

### 2.1 `autofocus` 属性

布尔属性，用于指定当页面加载时按钮必须有输入焦点。只有一个表单关联元素可以指定该属性。

### 2.2 `autocomplete` 属性

该属性在 `<button> `上的使用并未标准化，只有 Firefox 允许。

### 2.3 `disabled` 属性

布尔属性，表示用户不能与 button 交互。

### 2.4 `form` 属性

表示 `button` 元素关联的 `form` 元素（它的表单拥有者）。

此属性值必须为同一文档中的一个 `<form>` 元素的 id 属性。

如果此属性未指定，`<button>` 元素必须是 form 元素的后代。

利用此属性，你可以将 `<button>` 元素放置在文档内的任何位置，而不仅仅是作为他们 form 元素的后代。

### 2.5 `formaction` 属性

表示程序处理 button 提交信息的 URI。如果指定了，将重写 button 表单拥有者的 action 属性。

### 2.6 `formenctype` 属性

同 `form` 的 `enctype` 属性

### 2.7 `formmethod` 属性

同 `form` 的 `method` 属性

### 2.8 `formnovalidate` 属性

同 `form` 的 `novalidate` 属性

### 2.9 `formtarget` 属性

同 `form` 的 `target` 属性

### 2.10 `name` 属性

button 的名称，与表单数据一起提交。

### 2.11 `type` 属性

button 的类型。可选值：

- `submit`: 此按钮将表单数据提交给服务器。如果未指定属性，或者属性动态更改为空值或无效值，则此值为默认值。
- `reset`: 此按钮重置所有组件为初始值。
- `button`: 此按钮没有默认行为。它可以有与元素事件相关的客户端脚本，当事件出现时可触发。
- `menu`: 此按钮打开一个由指定 `<menu>` 元素进行定义的弹出菜单。

### 2.12 `value` 属性

button 的初始值。它定义的值与表单数据的提交按钮相关联。

当表单中的数据被提交时，这个值便以参数的形式被递送至服务器。

## 3. `<option>` 元素

用于定义在 `<select>`, `<optgroup>` 或 `<datalist>` 元素中包含的项。

### 3.1 `disabled` 属性

如果设置了这个布尔属性，则该选项不可选，并且不再接受任何浏览器事件。

如果这个属性没有设置，而这个元素的其中一个父元素是被禁用的 `<optgroup>` 元素，则这个元素仍然是禁用的。

### 3.2 `label` 属性

这个属性是用于表示选项含义的文本。如果 label 属性没有定义，它的值就是元素文本内容。

### 3.3 `selected` 属性

这个布尔属性存在时表明这个选项是否一开始就被选中。

### 3.4 `value` 属性

这个属性的值表示该选项被选中时提交给表单的值。如果省略了这个属性，值就从选项元素的文本内容中获取。

## 4. `<datalist>` 元素

包含了一组 `<option>` 元素，这些元素表示其它表单控件可选值。

```html
<label for="ice-cream-choice">Choose a flavor:</label>
<input list="ice-cream-flavors" id="ice-cream-choice" name="ice-cream-choice" />

<datalist id="ice-cream-flavors">
  <option value="Chocolate"></option>
  <option value="Coconut"></option>
  <option value="Mint"></option>
  <option value="Strawberry"></option>
  <option value="Vanilla"></option>
</datalist>
```

## 5. `<optgroup>` 元素

`<optgroup>` 为 `<select>` 元素中的选项创建分组。

```html
<label for="dino-select">Choose a dinosaur:</label>
<select id="dino-select">
  <optgroup label="Theropods">
    <option>Tyrannosaurus</option>
    <option>Velociraptor</option>
    <option>Deinonychus</option>
  </optgroup>
  <optgroup label="Sauropods">
    <option>Diplodocus</option>
    <option>Saltasaurus</option>
    <option>Apatosaurus</option>
  </optgroup>
</select>
```

### 5.1 `disabled` 属性

### 5.2 `label` 属性

选项组的名字，浏览器用以在用户界面中标记选项。使用这个元素时必须加上这个属性。

## 6. `<select>` 元素

表示一个提供选项菜单的控件。

### 6.1 `autocomplete` 属性

### 6.2 `autofocus` 属性

### 6.3 `disabled` 属性

### 6.4 `form` 属性

`<select>` 所关联的 `<form>`，未指定则为祖先 `<form>`。其值必须是在同一文档中的 `<form>` 元素的 id。

### 6.5 `multiple` 属性

布尔值属性表示列表中的选项是否支持多选。

### 6.6 `name` 属性

该属性规定了控件的名称。

### 6.7 `required` 属性

### 6.8 `size` 属性

此属性表示为控件中同时可见的行数。


## 7. `<fieldset>` 元素

用于对表单中的控制元素进行分组（也包括 label 元素）。

```html
<form>
  <fieldset>
    <legend>Choose your favorite monster</legend>

    <input type="radio" id="kraken" name="monster" />
    <label for="kraken">Kraken</label><br />

    <input type="radio" id="sasquatch" name="monster" />
    <label for="sasquatch">Sasquatch</label><br />

    <input type="radio" id="mothman" name="monster" />
    <label for="mothman">Mothman</label>
  </fieldset>
</form>
```

### 7.1 `disabled` 属性

如果设置了这个 bool 值属性, `<fieldset>` 的所有子代表单控件也会继承这个属性。

这意味着它们不可编辑，也不会随着 `<form>` 一起提交。它们也不会接收到任何浏览器事件，如鼠标点击或与聚焦相关的事件。

### 7.2 `form` 属性

### 7.3 `name` 属性

## 8. `<legend>` 元素

用于表示其父元素 `<fieldset>` 的内容标题。

## 9. `<label>` 元素

```html
<label>Click me <input type="text" /></label>

<label for="username">Click me</label>
<input type="text" id="username" />
```

表示用户界面中某个元素的说明。其主要有以下优点：

- 标签文本不仅与其相应的文本输入元素在视觉上相关联，同时当用户聚焦到这个表单输入元素时，
  屏幕阅读器可以读出标签，让使用辅助技术的用户更容易理解应输入什么数据。
- 可以点击关联的标签来聚焦或者激活这个输入元素，就像直接点击输入元素一样。
  这扩大了元素的可点击区域，让包括使用触屏设备在内的用户更容易激活这个元素。

### 9.1 `for` 属性

即和 `<label>` 元素在同一文档中的可关联标签的元素的 id。

### 9.2 `form` 属性

表示与 label 元素关联的 `<form>` 元素。如果声明了该属性，其值应是同一文档中 `<form>` 元素的 id。

## 10. `<output>` 元素

表示计算或用户操作的结果。

```html
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
  <input type="range" name="b" value="50" /> +
  <input type="number" name="a" value="10" /> =
  <output name="result"></output>
</form>
```

### 10.1. `for` 属性

其它影响计算结果的标签的 ID，可以多个。

### 10.2 `form` 属性

与当前标签有关联的 form。

### 10.2 `name` 属性


## 11. `<meter>` 元素

用来显示已知范围的标量值或者分数值。

### 11.1 `value` 属性

当前的数值。

### 11.2 `min` 属性

值域的最小边界值。默认值 0。

### 11.3 `max` 属性

值域的上限边界值。默认值 1。

### 11.4 `low` 属性

定义了低值区间的上限值。

### 11.5 `high` 属性

定义了低值区间的上限值。

### 11.5 `optimum` 属性

这个属性用来指示最优/最佳取值。

### 11.6 `form` 属性


## 12. `<progress>` 元素

用来显示一项任务的完成进度。

### 12.1 `max` 属性

### 12.2 `value` 属性


## 13. `<textarea>` 元素

表示一个多行纯文本编辑控件。

### 13.1 `autocomplete` 属性

### 13.2 `autofocus` 属性

### 13.3 `cols` `rows` 属性

文本域的可视宽度与高度。

### 13.4 `disabled` 属性

### 13.5 `form` 属性

### 13.6 `maxlength` `minlength` 属性

允许用户输入的最大、最小字符长度（Unicode) 。

### 13.7 `name` 属性

### 13.8 `placeholder` 属性

向用户提示可以在控件中输入的内容。

### 13.9 `readonly` 属性

不允许用户修改元素内文本。如果在表单里，这个元素的值还是会跟随表单一起提交。

### 13.10 `required` 属性

### 13.11 `spellcheck` 属性

该属性设为true时，表明该元素会做拼写和语法检查。

### 13.12 `wrap` 属性

指定文本换行的方式。可能的值为：

- hard: 在文本到达元素最大宽度的时候，浏览器自动插入换行符(CR+LF) 。比如指定 cols值。
  
- soft: 在到达元素最大宽度的时候，不会自动插入换行符。


## 14. `<input>` 元素

`<input>` 的工作方式相当程度上取决于 `type` 属性的值，不同的 `type` 会有不同的效果。

如果未指定此属性，则采用的默认类型为 text。
 
### 14.1 `type` 属性

- `button`， 没有默认行为的按钮
  
- `sumit`， 用于提交表单的按钮
  
- `reset`， 重置表单默认值的按钮，不推荐
  
- `image`， 带图像的 submit 按钮。

- `checkout`，复选框

- `radio`， 单选按钮，允许在多个拥有相同 name 值的选项中选中其中一个。

- `color`，颜色选择器

- `date`，日期选择控件，包括年月日，不包括时间
  
- `datetime-local`，日期选择控件，包括年月日时间
  
- `month`，年份和月份选择控件
  
- `week`，用于输入以年和周数组成的日期，不带时区。
  
- `time`，用于输入时间的控件，不包括时区。
  
- `text`，文本输入框，默认值
  
- `email`、`url`、`tel`、`file`、`number`、`password`、`search`、

- `range` 范围控件
  
- `hidden` 不显示的控件，其值仍会提交到服务器。
