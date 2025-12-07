---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(_:图像:来源:选择:内容:)
抓取时间：2025-12-01T02:45:57Z
---

# init(_:image:sources:selection:content:)

**Initializer**

创建一个与绑定集合绑定的选取器，该选取器通过字符串和图像资源生成标签。

### 声明

```swift
nonisolated init<C, S>(_ title: S, image: ImageResource, sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content) where C : RandomAccessCollection, S : StringProtocol, C.Element == Binding<SelectionValue>
```

## 参数

- **title**：描述选择选项目的的字符串。
- **image**：要查找的图像资源的名称。
- **sources**：用作显示拾取器选项来源的值集合。
- **selection**：决定当前所选选项的值的关键路径。当用户从选取器中选取一个选项时，`sources` 集合中所有项目的关键路径值都会根据所选选项进行更新。
- **content**：包含选项集的视图。

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
    "Border Thickness",
    sources: $selectedObjectBorders,
    selection: \.thickness
) {
    ForEach(Thickness.allCases) { thickness in
        Text(thickness.rawValue)
    }
}
```

## 创建带有图像标签的选取器

- **init(_:image:selection:content:)**：创建一个拾取器，该拾取器通过本地化字符串键和图像资源生成标签
- **init(_:systemImage:selection:content:)**：创建从本地化字符串键和系统图像生成标签的拾取器。
- **init(_:systemImage:sources:selection:content:)**：创建一个与绑定集合绑定的拾取器，该拾取器通过字符串生成标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:image:sources:selection:content:)
crawled: 2025-12-01T02:45:57Z
---

# init(_:image:sources:selection:content:)

**Initializer**

Creates a picker bound to a collection of bindings that generates its label from a string and image resource.

## Declaration

```swift
nonisolated init<C, S>(_ title: S, image: ImageResource, sources: C, selection: KeyPath<C.Element, Binding<SelectionValue>>, @ViewBuilder content: () -> Content) where C : RandomAccessCollection, S : StringProtocol, C.Element == Binding<SelectionValue>
```

## Parameters

- **title**: A string that describes the purpose of selecting an option.
- **image**: The name of the image resource to lookup.
- **sources**: A collection of values used as the source for displaying the Picker’s selection.
- **selection**: The key path of the values that determines the currently-selected options. When a user selects an option from the picker, the values at the key path of all items in the `sources` collection are updated with the selected option.
- **content**: A view that contains the set of options.

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
}
```

## Creating a picker with an image label

- **init(_:image:selection:content:)**: Creates a picker that generates its label from a localized string key and image resource
- **init(_:systemImage:selection:content:)**: Creates a picker that generates its label from a localized string key and system image.
- **init(_:systemImage:sources:selection:content:)**: Creates a picker bound to a collection of bindings that generates its label from a string.

