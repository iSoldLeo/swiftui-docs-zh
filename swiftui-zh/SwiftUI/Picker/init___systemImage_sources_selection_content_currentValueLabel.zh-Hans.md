---
源：https://developer.apple.com/documentation/SwiftUI/Picker/init(_:systemImage:sources:selection:content:currentValueLabel:)
抓取时间：2025-12-01T02:46:04Z


# init(_:systemImage:sources:selection:content:currentValueLabel:)

**Initializer**

创建绑定到绑定集合的拾取器，该拾取器接受自定义的当前值标签，并通过字符串生成标签。

### 声明

```swift
nonisolated init<C, S>(_ title: S, systemImage: String, sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View) where C : RandomAccessCollection, S : StringProtocol, C.Element == Binding<SelectionValue>
```

## 参数

- **title**：描述选择选项目的的字符串。
- **systemImage**：要查找的图像资源的名称。
- **sources**：用作显示拾取器选中内容来源的值集合。
- **selection**：决定当前所选选项的值的关键路径。当用户从选取器中选取一个选项时，`sources` 集合中所有项目的关键路径值都会根据所选选项进行更新。
- **content**：包含选项集的视图。
- **currentValueLabel**：包含选项集的视图：表示选取器当前值的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:systemImage:sources:selection:content:currentValueLabel:)
crawled: 2025-12-01T02:46:04Z
---

# init(_:systemImage:sources:selection:content:currentValueLabel:)

**Initializer**

Creates a picker bound to a collection of bindings that accepts a custom current value label and generates its label from a string.

## Declaration

```swift
nonisolated init<C, S>(_ title: S, systemImage: String, sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View) where C : RandomAccessCollection, S : StringProtocol, C.Element == Binding<SelectionValue>
```

## Parameters

- **title**: A string that describes the purpose of selecting an option.
- **systemImage**: The name of the image resource to lookup.
- **sources**: A collection of values used as the source for displaying the Picker’s selection.
- **selection**: The key path of the values that determines the currently-selected options. When a user selects an option from the picker, the values at the key path of all items in the `sources` collection are updated with the selected option.
- **content**: A view that contains the set of options.
- **currentValueLabel**: A view that represents the current value of the picker.

