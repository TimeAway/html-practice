# HTML 主根元素 - `<html>`

`<html>` 表示 HTML 的顶级元素，即 HTML 文档的根元素，其他元素都必须是此元素的后代。

## 1. `manifest` 属性

制定一个资源清单的 URI，指示应在本地缓存的资源。**该特性已经从 Web 标准中删除，尽量不要使用此特性，可改用 `service worker` 代替。**

## 2. `version` 属性

指定控制当前文档的 HTML 版本文档类型定义。**这个属性已不再需要**，因为这在文档类型声明中是多余的版本信息。

## 3. `xmlns` 属性

指派文档的 XML 命名空间。默认的值是 `http://www.w3.org/1999/xhtml` 。这在 XHTML 中是必要的，而在 HTML 中则是可选的。
