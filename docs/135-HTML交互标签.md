# HTML 交互标签

创建交互式用户界面对象的元素。

## 1. `<details>` 、`<summary>` 标签

可创建一个挂件，仅在被切换成展开状态时，它才会显示内含的信息。

`<summary>` 元素可为该部件提供概要或者标签。

```html
<details open>
    <summary>Details</summary>
    Something small enough to escape casual notice.
</details>
```

### 1.1 `open` 属性

布尔值，默认 `false`，表示是否展开内含信息。

通过如下事件，也可控制是否展开。

```javascript
details.addEventListener("toggle", event => {
  if (details.open) {
    /* 展开 */
  } else {
    /* 闭合 */
  }
});
```

## 2. `<dialog>` 元素

表示一个对话框或其他交互式组件，例如一个检查器或者窗口。

### 2.1 `open` 属性

指示这个对话框是激活的和能互动的。当这个 open 特性没有被设置，对话框不应该显示给用户。

**使用备注：**

- `<form>` 元素可在此对话框中使用，但需要指定属性 `method="dialog"`。
  当提交表单时，对话框的 `returnValue` 属性将会等于表单中被使用的提交按钮的 `value`。
- `::backdrop` CSS 伪元素可用于更改 `<dialog>` 背景元素样式，例如在对话框被打开激活时，
  调暗背景中不可访问的内容。仅当使用  `HTMLDialogElement.showModal()`  显示对话框时才会绘制 `backdrop` 背景。
