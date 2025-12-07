--- 来源：https://developer.apple.com/documentation/SwiftUI/View/formStyle(_:)

抓取时间：2025-12-02T17:23:46Z

---

# formStyle(_:)

**实例方法**

设置视图层级结构中表单的样式。

## 声明

```swift
nonisolated func formStyle<S>(_ style: S) -> some View where S : FormStyle

```

## 参数

- **style**：要设置的表单样式。

## 返回值

一个使用指定表单样式的视图，该视图及其子视图均应用了该样式。

## 输入分组

- **Form**：用于分组数据输入控件的容器，例如设置或检查器中的控件。

- **LabeledContent**：用于将标签附加到包含值的视图的容器。

- **labeledContentStyle(_:)**：设置标签内容的样式。


---
source: https://developer.apple.com/documentation/SwiftUI/View/formStyle(_:)
crawled: 2025-12-02T17:23:46Z
---

# formStyle(_:)

**Instance Method**

Sets the style for forms in a view hierarchy.

## Declaration

```swift
nonisolated func formStyle<S>(_ style: S) -> some View where S : FormStyle

```

## Parameters

- **style**: The form style to set.

## Return Value

A view that uses the specified form style for itself and its child views.

## Grouping inputs

- **Form**: A container for grouping controls used for data entry, such as in settings or inspectors.
- **LabeledContent**: A container for attaching a label to a value-bearing view.
- **labeledContentStyle(_:)**: Sets a style for labeled content.

