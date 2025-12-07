---
来源：https://developer.apple.com/documentation/SwiftUI/DisclosureTableRow/init(_:isExpanded:content:)
抓取时间： 2025-12-01T11:30:56Z
---

# init(_:isExpanded:content:)

**Initializer**

用给定的值和表格行创建一个披露组，并绑定到展开状态（展开或折叠）。

### 声明

```swift
init<Value>(_ value: Value, isExpanded: Binding<Bool>? = nil, @TableRowBuilder<Value> content: @escaping () -> Content) where Label == TableRow<Value>, Value == Content.TableRowValue
```

## 参数

- **value**：可披露表行的值。
- **isExpanded**：与布尔值的绑定，布尔值决定分组的展开状态（展开或折叠）。
- **content**：披露组展开时显示的表格行。


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureTableRow/init(_:isExpanded:content:)
crawled: 2025-12-01T11:30:56Z
---

# init(_:isExpanded:content:)

**Initializer**

Creates a disclosure group with the given value and table rows, and a binding to the expansion state (expanded or collapsed).

## Declaration

```swift
init<Value>(_ value: Value, isExpanded: Binding<Bool>? = nil, @TableRowBuilder<Value> content: @escaping () -> Content) where Label == TableRow<Value>, Value == Content.TableRowValue
```

## Parameters

- **value**: The value of the disclosable table row.
- **isExpanded**: A binding to a Boolean value that determines the group’s expansion state (expanded or collapsed).
- **content**: The table row shown when the disclosure group expands.

