---
来源： https://developer.apple.com/documentation/SwiftUI/ToggleStyle/checkbox
抓取时间： 2025-12-03T06:09:48Z
---

# 复选框

**类型属性**

一种切换样式，显示复选框及其标签。

## 声明

```swift
@MainActor @preconcurrency static var checkbox: CheckboxToggleStyle { get }
```

## 讨论

使用[Toggle](../Toggle.zh-Hans.md)修饰符将此样式应用于[Toggle](../Toggle.zh-Hans.md) 或包含切换器的视图层次结构：

```swift
Toggle("Close windows when quitting an app", isOn: $doesClose)
    .toggleStyle(.checkbox)
```

该样式会产生一个描述切换目的的标签和一个显示切换状态的复选框。要改变切换状态，用户需要点击复选框或其标签：



该样式将复选框的尾部边缘与标签的前部边缘对齐，并根据标签的大小占用所需的水平空间，最多不超过切换框父视图所提供的空间。

在 macOS 中的大多数情况下，如果不设置样式，或应用[automatic](automatic.zh-Hans.md)样式，则默认使用这种样式。[Form](../Form.zh-Hans.md)是以适当间距和对齐方式显示复选框集合的便捷方法。有关在用户界面中使用复选框的指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/toggles#Checkboxes]。

## 获取内置切换样式

- **automatic**：默认切换样式。
- **button**：以按钮形式显示的切换样式，其标签为标题。
- **switch**：显示前标签和后开关的切换样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle/checkbox
crawled: 2025-12-03T06:09:48Z
---

# checkbox

**Type Property**

A toggle style that displays a checkbox followed by its label.

## Declaration

```swift
@MainActor @preconcurrency static var checkbox: CheckboxToggleStyle { get }
```

## Discussion

Apply this style to a [Toggle](../Toggle.zh-Hans.md) or to a view hierarchy that contains toggles using the [toggleStyle(_:)](../View/toggleStyle.zh-Hans.md) modifier:

```swift
Toggle("Close windows when quitting an app", isOn: $doesClose)
    .toggleStyle(.checkbox)
```

The style produces a label that describes the purpose of the toggle and a checkbox that shows the toggle’s state. To change the toggle’s state, the user clicks the checkbox or its label:



The style aligns the trailing edge of the checkbox with the leading edge of the label, and takes as much horizontal space as it needs to fit the label, up to the amount offered by the toggle’s parent view.

This is the default style in macOS in most contexts when you don’t set a style, or when you apply the [automatic](automatic.zh-Hans.md) style. A [Form](../Form.zh-Hans.md) is a convenient way to present a collection of checkboxes with proper spacing and alignment. For guidance on using checkboxes in your user interface, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/toggles#Checkboxes] in the Human Interface Guidelines.

## Getting built-in toggle styles

- **automatic**: The default toggle style.
- **button**: A toggle style that displays as a button with its label as the title.
- **switch**: A toggle style that displays a leading label and a trailing switch.

