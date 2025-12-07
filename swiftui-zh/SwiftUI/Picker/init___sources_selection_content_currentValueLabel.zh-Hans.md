---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:sources:selection:content:currentValueLabel:)
抓取时间：2025-12-01T02:46:02Z
---

# init(_:sources:selection:content:currentValueLabel:)

**Initializer**

创建绑定到绑定集合的拾取器，该拾取器通过字符串生成标签，并接受自定义的当前值标签。

### 声明

```swift
nonisolated init<C, S>(_ title: S, sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View) where C : RandomAccessCollection, S : StringProtocol
```

## 参数

- **title**：描述选择选项目的的字符串。
- **sources**：用作显示拾取器选项来源的值集合。
- **selection**：决定当前所选选项的值的关键路径。当用户从选取器中选取一个选项时，`sources` 集合中所有项目的关键路径值都会根据所选选项进行更新。
- **content**：包含选项集的视图。
- **currentValueLabel**：包含选项集的视图：表示选取器当前值的视图。

## 讨论

如果传递给`sources` 的集合的包装值不完全相同，某些样式会以混合状态显示选择项。具体呈现方式取决于样式。  例如，具有菜单样式的拾取器使用破折号而不是复选标记来表示所选值。

在下面的示例中，文档检查器中的选取器可以控制当前选中图形的边框粗细，边框可以是任意数量。

```swift
enum Thickness: String, CaseIterable, Identifiable {
    case thin
    case regular
    case thick

    var id: String { rawValue }
}

struct Border {
    var color: Color
    var thickness: Thickness
}

@State private var selectedObjectBorders = [
    Border(color: .black, thickness: .thin),
    Border(color: .red, thickness: .thick)
]

Picker(
    "Border Thickness",
    sources: $selectedObjectBorders,
    selection: \.thickness
) {
    ForEach(Thickness.allCases) { thickness in
        Text(thickness.rawValue)
    }
} currentValueLabel: {
     switch selectedObjectBorders.count {
        case 0: Text("None")
        case 1: Text(selectedObjectBorders[0].thickness.rawValue)
        default: Text("Multiple")
     }
}
```

此初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图。有关字符串本地化的更多信息，请参见 [Text](../Text.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:sources:selection:content:currentValueLabel:)
crawled: 2025-12-01T02:46:02Z
---

# init(_:sources:selection:content:currentValueLabel:)

**Initializer**

Creates a picker bound to a collection of bindings that generates its label from a string and accepts a custom current value label.

## Declaration

```swift
nonisolated init<C, S>(_ title: S, sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View) where C : RandomAccessCollection, S : StringProtocol
```

## Parameters

- **title**: A string that describes the purpose of selecting an option.
- **sources**: A collection of values used as the source for displaying the Picker’s selection.
- **selection**: The key path of the values that determines the currently-selected options. When a user selects an option from the picker, the values at the key path of all items in the `sources` collection are updated with the selected option.
- **content**: A view that contains the set of options.
- **currentValueLabel**: A view that represents the current value of the picker.

## Discussion

If the wrapped values of the collection passed to `sources` are not all the same, some styles render the selection in a mixed state. The specific presentation depends on the style.  For example, a Picker with a menu style uses dashes instead of checkmarks to indicate the selected values.

In the following example, a picker in a document inspector controls the thickness of borders for the currently-selected shapes, which can be of any number.

```swift
enum Thickness: String, CaseIterable, Identifiable {
    case thin
    case regular
    case thick

    var id: String { rawValue }
}

struct Border {
    var color: Color
    var thickness: Thickness
}

@State private var selectedObjectBorders = [
    Border(color: .black, thickness: .thin),
    Border(color: .red, thickness: .thick)
]

Picker(
    "Border Thickness",
    sources: $selectedObjectBorders,
    selection: \.thickness
) {
    ForEach(Thickness.allCases) { thickness in
        Text(thickness.rawValue)
    }
} currentValueLabel: {
     switch selectedObjectBorders.count {
        case 0: Text("None")
        case 1: Text(selectedObjectBorders[0].thickness.rawValue)
        default: Text("Multiple")
     }
}
```

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf. See [Text](../Text.zh-Hans.md) for more information about localizing strings.

