---
来源： https://developer.apple.com/documentation/SwiftUI/ToggleStyle/button
抓取时间： 2025-12-03T06:09:47Z
---

# 按钮

**类型属性**

切换样式，显示为按钮，其标签为标题。

### 声明

```swift
@MainActor @preconcurrency static var button: ButtonToggleStyle { get }
```

## 讨论

使用[toggleStyle(_:)](../View/toggleStyle.zh-Hans.md)修饰符将此样式应用于[Toggle](../Toggle.zh-Hans.md) 或包含切换器的视图层次结构：

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```

该样式会生成一个按钮，按钮上的标签说明了切换的目的。用户轻按或单击该按钮可更改切换状态。该按钮通过在背景中填充颜色来显示`on` 状态。您可以使用[tint(_:)](../View/tint.zh-Hans.md) 修改器更改着色颜色。SwiftUI 将此样式作为出现在工具栏中的切换按钮的默认样式。

下表分别显示了 `off` 和 `on` 状态下的切换：



[Label](../Label.zh-Hans.md)实例是按钮切换标签的最佳选择。SwiftUI 会根据上下文决定是同时显示标题和图标（如上面的示例），还是只显示图标（如切换按钮出现在工具栏中）。您还可以通过添加[labelStyle(_:)](../View/labelStyle.zh-Hans.md)修饰符来控制标签的样式。无论如何，SwiftUI 总是使用标题来识别使用 VoiceOver 的控件。

## 获取内置的切换样式

- **automatic**：默认切换样式。
- **checkbox**：显示复选框及其标签的切换样式。
- **switch**：显示前标签和后开关的切换样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle/button
crawled: 2025-12-03T06:09:47Z
---

# button

**Type Property**

A toggle style that displays as a button with its label as the title.

## Declaration

```swift
@MainActor @preconcurrency static var button: ButtonToggleStyle { get }
```

## Discussion

Apply this style to a [Toggle](../Toggle.zh-Hans.md) or to a view hierarchy that contains toggles using the [toggleStyle(_:)](../View/toggleStyle.zh-Hans.md) modifier:

```swift
Toggle(isOn: $isFlagged) {
    Label("Flag", systemImage: "flag.fill")
}
.toggleStyle(.button)
```

The style produces a button with a label that describes the purpose of the toggle. The user taps or clicks the button to change the toggle’s state. The button indicates the `on` state by filling in the background with its tint color. You can change the tint color using the [tint(_:)](../View/tint.zh-Hans.md) modifier. SwiftUI uses this style as the default for toggles that appear in a toolbar.

The following table shows the toggle in both the `off` and `on` states, respectively:



A [Label](../Label.zh-Hans.md) instance is a good choice for a button toggle’s label. Based on the context, SwiftUI decides whether to display both the title and icon, as in the example above, or just the icon, like when the toggle appears in a toolbar. You can also control the label’s style by adding a [labelStyle(_:)](../View/labelStyle.zh-Hans.md) modifier. In any case, SwiftUI always uses the title to identify the control using VoiceOver.

## Getting built-in toggle styles

- **automatic**: The default toggle style.
- **checkbox**: A toggle style that displays a checkbox followed by its label.
- **switch**: A toggle style that displays a leading label and a trailing switch.

