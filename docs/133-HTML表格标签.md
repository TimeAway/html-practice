# HTML 表格标签

```html
<table>
    <caption>Council budget (in £) 2018</caption>
    <colgroup>
        <col>
        <col span="2">
        <col span="2">
    </colgroup>
    <thead>
    <tr>
        <th>Items</th>
        <th scope="col">Expenditure</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <th scope="row">Donuts</th>
        <td>3,000</td>
    </tr>
    <tr>
        <th scope="row">Stationery</th>
        <td>18,000</td>
    </tr>
    </tbody>
    <tfoot>summary</tfoot>
</table>
```

## 1. `<caption>` 标签

`<caption>` 元素展示表格的标题， 它常常作为 `<table>` 的第一个子元素出现，同时显示在表格内容的最前面。

## 2. `<colgroup>`、`<col>` 标签

前者定义表格中的列组，后者定义表格中的列，位于 `<colgroup>` 元素内，并用于定义所有公共单元格上的公共语义。

### 2.1 `<col>` - `span` 属性

该属性值为一个正整数，表示该 `<col>` 元素横跨的列数。默认值为 1。

## 3. `<thead>`、`<tbody>`、`<tfoot>` 标签

- `<thead>` 定义了一组定义表格的列头的行

- `<tbody>` 表格的主体内容

- `<tfoot>` 定义了一组表格中各列的汇总行

## 4. `<tr>`、`<th>`、`<td>` 标签

- `<tr>` 定义表格中的行
  
- `<th>` 定义表格内的表头单元格
  
- `<td>` 定义了一个包含数据的表格单元格

### 4.1 `colspan`

默认值 1，表示单元格拓展列的数量，最大 1000。

### 4.2 `rowspan`

默认值 1，表示单元格拓展行的数量，最大 65534。

### 4.3 `headers`

这个属性包含了一个空间分隔的字符串的列表, 每个与其他 `<th>` 元素相关联的 id 属性一一对应。

### 4.4 `scope`

这个枚举属性定义了表头元素 (在 `<th>` 中定义) 关联的单元格。它可能有以下值：

- `row`:  表头关联一行中所有的单元格。
  
- `col`: 表头关联一列中所有的单元格。
  
- `rowgroup`: 表头属于一个行组并与其中所有单元格相关联。这些单元格可以被放在表头的左侧或右侧，
  取决于 `<table>` 元素中 dir 属性的值。
  
- `colgroup`: 表头属于一个列组并与其中所有单元格相关联。
  
- `auto`
