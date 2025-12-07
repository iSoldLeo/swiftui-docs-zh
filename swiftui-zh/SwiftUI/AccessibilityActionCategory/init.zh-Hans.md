---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityActionCategory/init(_:)
抓取时间： 2025-12-01T11:38:19Z
---

# init(_:)

**Initializer**

创建一个由 `name` 标记的自定义动作类别。

### 声明

```swift
init(_ name: Text)
```

## 讨论

扩展无障碍操作类别 { static let table = AccessibilityActionCategory("Table Options") }

var body: some View { TableCellView() .accessibilityActions(category: .table) { ForEach(tableCellActions) { action in Button(action.title) { action() }}}}

- 参数：

- name：无障碍操作类别的名称。


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityActionCategory/init(_:)
crawled: 2025-12-01T11:38:19Z
---

# init(_:)

**Initializer**

Creates a custom action category labeled by `name`.

## Declaration

```swift
init(_ name: Text)
```

## Discussion

Extension AccessibilityActionCategory { static let table = AccessibilityActionCategory(“Table Options”) }

var body: some View { TableCellView() .accessibilityActions(category: .table) { ForEach(tableCellActions) { action in Button(action.title) { action() } } } }

- Parameter:

- name: The name for the category of the accessibility actions.

