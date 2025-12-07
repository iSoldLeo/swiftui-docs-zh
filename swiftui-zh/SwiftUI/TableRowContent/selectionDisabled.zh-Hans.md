--- 来源：https://developer.apple.com/documentation/SwiftUI/TableRowContent/selectionDisabled(_:)

抓取时间：2025-12-01T11:30:35Z

---

# selectionDisabled(_:)

**实例方法**

添加一个条件，用于控制用户是否可以选择此行。

## 声明

```swift
@MainActor @preconcurrency func selectionDisabled(_ isDisabled: Bool = true) -> some TableRowContent<Self.TableRowValue>

```

## 参数

- **isDisabled**：一个布尔值，用于确定用户是否可以选择此行。

## 说明

使用此修饰符可以控制可选择容器（例如 [List](../List.zh-Hans.md) 或 [Table](../Table.zh-Hans.md)）中视图的可选择性。在下面的示例中，用户无法选择表格中的第一个项目。

```swift
@Binding var rows: [Item]
@Binding var selection: Set<Item.ID>

var body: some View {
    Table(of: Item.self, selection: $selection) {
        TableColumn("ID", value: \.id.uuidString)
    } rows: {
        ForEach(rows) { row in
            TableRow(row)
                .selectionDisabled(
                    row.id == rows.first?.id
                )
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


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowContent/selectionDisabled(_:)
crawled: 2025-12-01T11:30:35Z
---

# selectionDisabled(_:)

**Instance Method**

Adds a condition that controls whether users can select this row.

## Declaration

```swift
@MainActor @preconcurrency func selectionDisabled(_ isDisabled: Bool = true) -> some TableRowContent<Self.TableRowValue>

```

## Parameters

- **isDisabled**: A Boolean value that determines whether users can select this row.

## Discussion

Use this modifier to control the selectability of views in selectable containers like [List](../List.zh-Hans.md) or [Table](../Table.zh-Hans.md). In the example, below, the user can’t select the first item in the table.

```swift
@Binding var rows: [Item]
@Binding var selection: Set<Item.ID>

var body: some View {
    Table(of: Item.self, selection: $selection) {
        TableColumn("ID", value: \.id.uuidString)
    } rows: {
        ForEach(rows) { row in
            TableRow(row)
                .selectionDisabled(
                    row.id == rows.first?.id
                )
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

