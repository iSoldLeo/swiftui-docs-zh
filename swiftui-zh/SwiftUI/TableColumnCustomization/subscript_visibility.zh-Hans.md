--- 来源：https://developer.apple.com/documentation/SwiftUI/TableColumnCustomization/subscript(visibility:)

抓取时间：2025-12-01T09:06:10Z

---

# subscript(visibility:)

**实例下标**

指定由其标识符标识的列的可见性。

## 声明

```swift
subscript(visibility id: String) -> Visibility { get set }
```

## 概述

可以使用 `customizationID(_:)` 修饰符将显式标识符与 `TableColumn` 关联。

```swift
TableColumn("Number of Reports", value: \.duplicateCount) {
    Text($0.duplicateCount, format: .number)
}
.customizationID("numberOfReports")

...

columnsCustomization[visibility: "numberOfReports"] = .hidden
```

如果 ID 未与状态关联，则返回默认值 `.automatic`。

## 管理自定义设置

- **resetOrder()**：将列顺序重置为默认值，但保留自定义的可见性和大小。


---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnCustomization/subscript(visibility:)
crawled: 2025-12-01T09:06:10Z
---

# subscript(visibility:)

**Instance Subscript**

The visibility of the column identified by its identifier.

## Declaration

```swift
subscript(visibility id: String) -> Visibility { get set }
```

## Overview

Explicit identifiers can be associated with a `TableColumn` using the `customizationID(_:)` modifier.

```swift
TableColumn("Number of Reports", value: \.duplicateCount) {
    Text($0.duplicateCount, format: .number)
}
.customizationID("numberOfReports")

...

columnsCustomization[visibility: "numberOfReports"] = .hidden
```

If the ID isn’t associated with the state, a default value of `.automatic` is returned.

## Managing the customization

- **resetOrder()**: Resets the column order back to the default, preserving the customized visibility and size.

