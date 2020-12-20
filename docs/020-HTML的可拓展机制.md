# HTML 的可拓展机制

- 通过使用 `class` 元素拓展属性

- 通过使用 `data-*=` 属性来包含数据

- 通过 `rel` 机制，给链接标注特定的含义，具体可见 [Link Type Extensions](http://microformats.org/wiki/existing-rel-values#HTML5_link_type_extensions)

- 通过 `<meta name="" content="">` 机制， 可以为预定义的元数据名称的集合注册扩展 来引入页面级别的元数据。

- 通过使用 `<script type="">` 来内嵌自定义类型的原始数据，用于在内联脚本或服务器端脚本中做进一步处理。

- 通过使用 `embed` 元素，作者可以创建插件和调用他们。这就是 Flash 的工作原理。

- 通过使用 JavaScript 原型机制来扩展 API。这在脚本库中有广泛的使用。

- 通过使用微数据特性（`itemscope=""` 和 `itemprop=""` 属性） 来嵌入嵌套的键值对数据，以供其他应用和站点共享。
