--- 来源：https://developer.apple.com/documentation/SwiftUI/View/indexViewStyle(_:)

抓取时间：2025-12-02T17:33:35Z

---

# indexViewStyle(_:)

**实例方法**

设置当前环境中索引视图的样式。

## 声明

```swift
nonisolated func indexViewStyle<S>(_ style: S) -> some View where S : IndexViewStyle

```

## 参数

- **style**：要应用于此视图的样式。

## 样式组

- **controlGroupStyle(_:)**：设置此视图中控件组的样式。

- **ControlGroupStyle**：定义视图层次结构中所有控件组的实现。

- **ControlGroupStyleConfiguration**：控件组的属性。

- **formStyle(_:)**：设置视图层次结构中表单的样式。

- **FormStyle**：表单的外观和行为。

- **FormStyleConfiguration**：表单实例的属性。

- **groupBoxStyle(_:)**：设置此视图中分组框的样式。

- **GroupBoxStyle**：指定视图层次结构中所有分组框的外观和交互方式的类型。

- **GroupBoxStyleConfiguration**：分组框实例的属性。

- **IndexViewStyle**：定义视图层次结构中所有 `IndexView` 实例的实现。

- **labeledContentStyle(_:)**：设置标签内容的样式。

- **LabeledContentStyle**：已标记内容实例的外观和行为。

- **LabeledContentStyleConfiguration**：已标记内容实例的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/indexViewStyle(_:)
crawled: 2025-12-02T17:33:35Z
---

# indexViewStyle(_:)

**Instance Method**

Sets the style for the index view within the current environment.

## Declaration

```swift
nonisolated func indexViewStyle<S>(_ style: S) -> some View where S : IndexViewStyle

```

## Parameters

- **style**: The style to apply to this view.

## Styling groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
- **ControlGroupStyle**: Defines the implementation of all control groups within a view hierarchy.
- **ControlGroupStyleConfiguration**: The properties of a control group.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **FormStyle**: The appearance and behavior of a form.
- **FormStyleConfiguration**: The properties of a form instance.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.
- **GroupBoxStyle**: A type that specifies the appearance and interaction of all group boxes within a view hierarchy.
- **GroupBoxStyleConfiguration**: The properties of a group box instance.
- **IndexViewStyle**: Defines the implementation of all `IndexView` instances within a view hierarchy.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **LabeledContentStyle**: The appearance and behavior of a labeled content instance..
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

