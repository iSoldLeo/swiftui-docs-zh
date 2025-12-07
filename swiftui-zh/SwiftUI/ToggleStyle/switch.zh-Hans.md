---
来源： https://developer.apple.com/documentation/SwiftUI/ToggleStyle/switch
抓取时间： 2025-12-03T06:09:49Z
---

# 开关

**类型属性**

切换样式，显示前面的标签和后面的开关。

## 声明

```swift
@MainActor @preconcurrency static var `switch`: SwitchToggleStyle { get }
```

## 讨论

使用[Toggle](../Toggle.zh-Hans.md)修饰符将此样式应用于[Toggle](../Toggle.zh-Hans.md) 或包含切换器的视图层次结构：

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.switch)
```

该样式会产生一个描述切换器用途的标签和一个显示切换器状态的开关。用户点击或单击开关即可改变切换开关的状态。尽管在用户界面中使用开关的方式略有不同，但各平台的默认外观是相似的，详见《人机界面指南》中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/toggles]。



在 iOS、iPadOS、watchOS 和 tvOS 中，通过将标签的前缘和开关的后缘与包含视图各自的前缘和后缘对齐，标签和开关所占的水平空间与切换开关的父视图所占的水平空间相同。在 macOS 中，该样式将标签的尾部边缘与开关的前部边缘对齐，从而使用最少的水平空间。当此样式出现在[Form](../Form.zh-Hans.md)中时，SwiftUI 可以帮助您管理间距和对齐方式。

当您未设置样式或应用[automatic](automatic.zh-Hans.md)样式时，SwiftUI 会在大多数情况下将此样式作为 iOS、iPadOS、watchOS 和 tvOS 的默认样式。

## 获取内置切换样式

- **automatic**：默认的切换样式。
- **button**：以按钮形式显示的切换样式，其标签为标题。
- **checkbox**：一种切换样式，显示一个复选框，后面跟有标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle/switch
crawled: 2025-12-03T06:09:49Z
---

# switch

**Type Property**

A toggle style that displays a leading label and a trailing switch.

## Declaration

```swift
@MainActor @preconcurrency static var `switch`: SwitchToggleStyle { get }
```

## Discussion

Apply this style to a [Toggle](../Toggle.zh-Hans.md) or to a view hierarchy that contains toggles using the [toggleStyle(_:)](../View/toggleStyle.zh-Hans.md) modifier:

```swift
Toggle("Enhance Sound", isOn: $isEnhanced)
    .toggleStyle(.switch)
```

The style produces a label that describes the purpose of the toggle and a switch that shows the toggle’s state. The user taps or clicks the switch to change the toggle’s state. The default appearance is similar across platforms, although the way you use switches in your user interface varies a little, as described in [doc://com.apple.documentation/design/Human-Interface-Guidelines/toggles] in the Human Interface Guidelines.



In iOS, iPadOS, watchOS, and tvOS, the label and switch fill as much horizontal space as the toggle’s parent offers by aligning the label’s leading edge and the switch’s trailing edge with the containing view’s respective leading and trailing edges. In macOS, the style uses a minimum of horizontal space by aligning the trailing edge of the label with the leading edge of the switch. SwiftUI helps you to manage the spacing and alignment when this style appears in a [Form](../Form.zh-Hans.md).

SwiftUI uses this style as the default for iOS, iPadOS, watchOS, and tvOS in most contexts when you don’t set a style, or when you apply the [automatic](automatic.zh-Hans.md) style.

## Getting built-in toggle styles

- **automatic**: The default toggle style.
- **button**: A toggle style that displays as a button with its label as the title.
- **checkbox**: A toggle style that displays a checkbox followed by its label.

