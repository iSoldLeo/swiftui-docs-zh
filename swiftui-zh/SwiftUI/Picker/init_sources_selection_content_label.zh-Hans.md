---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(来源：选择：内容：标签：)
抓取时间：2025-12-01T02:45:56Z
---

# init(sources:selection:content:label:)

**Initializer**

创建显示自定义标签的选取器。

## 声明

```swift
nonisolated init<C>(sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label) where C : RandomAccessCollection
```

## 参数

- **sources**：用于显示拾取器选中内容的源值集合。
- **selection**：决定当前所选选项的值的关键路径。当用户从选取器中选取一个选项时，`sources` 集合中所有项目的关键路径值都会根据所选选项进行更新。
- **content**：包含选项集的视图。
- **label**：包含选项集的视图：描述选项选择目的的视图。

## 讨论

如果传递给 `sources` 的集合的包装值不完全相同，某些样式会以混合状态显示选择。具体呈现方式取决于样式。  例如，具有菜单样式的拾取器使用破折号而不是复选标记来表示所选值。

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
    sources: $selectedObjectBorders,
    selection: \.thickness
) {
    ForEach(Thickness.allCases) { thickness in
        Text(thickness.rawValue)
    }
} label: {
    Text("Border Thickness")
}
```

## 为集合创建选取器

- **init(_:sources:selection:content:)**：创建一个与绑定集合绑定的拾取器，该拾取器的标签由字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(sources:selection:content:label:)
crawled: 2025-12-01T02:45:56Z
---

# init(sources:selection:content:label:)

**Initializer**

Creates a picker that displays a custom label.

## Declaration

```swift
nonisolated init<C>(sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label) where C : RandomAccessCollection
```

## Parameters

- **sources**: A collection of values used as the source for displaying the Picker’s selection.
- **selection**: The key path of the values that determines the currently-selected options. When a user selects an option from the picker, the values at the key path of all items in the `sources` collection are updated with the selected option.
- **content**: A view that contains the set of options.
- **label**: A view that describes the purpose of selecting an option.

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
    sources: $selectedObjectBorders,
    selection: \.thickness
) {
    ForEach(Thickness.allCases) { thickness in
        Text(thickness.rawValue)
    }
} label: {
    Text("Border Thickness")
}
```

## Creating a picker for a collection

- **init(_:sources:selection:content:)**: Creates a picker bound to a collection of bindings that generates its label from a string.

