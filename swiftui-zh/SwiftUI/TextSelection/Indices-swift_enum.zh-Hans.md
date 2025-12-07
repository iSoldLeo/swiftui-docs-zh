---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelection/Indices-swift.enum
抓取时间： 2025-12-03T06:17:38Z
---

# TextSelection.Indices

**Enumeration**

当前选区的索引。

## 声明

```swift
enum Indices
```

## 枚举案例

- **TextSelection.Indices.multiSelection(_:)**：选择的范围集。
- **TextSelection.Indices.selection(_:)**：单个选区的范围。如果`range.lowerBound == range.upperBound`.

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelection/Indices-swift.enum
crawled: 2025-12-03T06:17:38Z
---

# TextSelection.Indices

**Enumeration**

The indices of the current selection.

## Declaration

```swift
enum Indices
```

## Enumeration Cases

- **TextSelection.Indices.multiSelection(_:)**: The range-set of the selections.
- **TextSelection.Indices.selection(_:)**: The range of the single selection. This may also an represent insertion points if `range.lowerBound == range.upperBound`.

## Conforms To

- Equatable
- Hashable

