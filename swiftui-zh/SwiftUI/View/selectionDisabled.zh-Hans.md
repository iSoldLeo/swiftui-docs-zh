--- 来源：https://developer.apple.com/documentation/SwiftUI/View/selectionDisabled(_:)

抓取时间：2025-12-02T17:39:44Z

---

# selectionDisabled(_:)

**实例方法**

添加一个条件，用于控制用户是否可以选择此视图。

## 声明

```swift
nonisolated func selectionDisabled(_ isDisabled: Bool = true) -> some View

```

## 参数

- **isDisabled**：一个布尔值，用于确定用户是否可以选择此视图。

## 说明

使用此修饰符可以控制可选择容器（例如 [List](../List.zh-Hans.md) 或 [Table](../Table.zh-Hans.md)）中视图的可选择性。在下面的示例中，用户无法选择列表中的第一个项目。

```swift
@Binding var selection: Item.ID?
@Binding var items: [Item]

var body: some View {
    List(selection: $selection) {
        ForEach(items) { item in
            ItemView(item: item)
                .selectionDisabled(item.id == items.first?.id)
        }
    }
}
```

您还可以使用此修饰符来指定 `Picker` 中视图的可选择性。以下示例表示一个口味选择器，它会禁用对不可用口味的选择。

```swift
Picker("Flavor", selection: $selectedFlavor) {
    ForEach(Flavor.allCases) { flavor in
        Text(flavor.rawValue.capitalized)
            .selectionDisabled(isSoldOut(flavor))
    }
}
```

## 配置交互

- **swipeActions(edge:allowsFullSwipe:content:)**：为列表中的某一行添加自定义滑动操作。

- **listRowHoverEffect(_:)**：请求包含该行的列表行使用提供的悬停效果。

- **listRowHoverEffectDisabled(_:)**：请求禁用包含该行的列表行的悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/selectionDisabled(_:)
crawled: 2025-12-02T17:39:44Z
---

# selectionDisabled(_:)

**Instance Method**

Adds a condition that controls whether users can select this view.

## Declaration

```swift
nonisolated func selectionDisabled(_ isDisabled: Bool = true) -> some View

```

## Parameters

- **isDisabled**: A Boolean value that determines whether users can select this view.

## Discussion

Use this modifier to control the selectability of views in selectable containers like [List](../List.zh-Hans.md) or [Table](../Table.zh-Hans.md). In the example, below, the user can’t select the first item in the list.

```swift
@Binding var selection: Item.ID?
@Binding var items: [Item]

var body: some View {
    List(selection: $selection) {
        ForEach(items) { item in
            ItemView(item: item)
                .selectionDisabled(item.id == items.first?.id)
        }
    }
}
```

You can also use this modifier to specify the selectability of views within a `Picker`. The following example represents a flavor picker that disables selection on flavors that are unavailable.

```swift
Picker("Flavor", selection: $selectedFlavor) {
    ForEach(Flavor.allCases) { flavor in
        Text(flavor.rawValue.capitalized)
            .selectionDisabled(isSoldOut(flavor))
    }
}
```

## Configuring interaction

- **swipeActions(edge:allowsFullSwipe:content:)**: Adds custom swipe actions to a row in a list.
- **listRowHoverEffect(_:)**: Requests that the containing list row use the provided hover effect.
- **listRowHoverEffectDisabled(_:)**: Requests that the containing list row have its hover effect disabled.

