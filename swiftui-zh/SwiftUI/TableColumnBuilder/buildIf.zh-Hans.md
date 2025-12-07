---
来源： https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildIf(_:)
抓取时间： 2025-12-03T06:40:54Z
---

# buildIf(_:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ TableColumnBuilder ](/documentation/swiftui/tablecolumnbuilder)

- [ buildIf(_:) ](/documentation/SwiftUI/TableColumnBuilder/buildIf(_:))

- [ TableColumnBuilder ](/documentation/swiftui/tablecolumnbuilder)

- buildIf(_:)

类型 方法# buildIf(_:)

iOS 17.4+iPadOS 17.4+Mac Catalyst 17.4+macOS 14.4+visionOS 1.1+

```
static func buildIf<C>(_ content: C?) -> C? where RowValue == C.TableRowValue, C : TableColumnContent, C.TableColumnSortComparator == Never
```

当 `RowValue` 符合 `Identifiable` 和 `Sort` 符合 `SortComparator` 时可用。显示所有声明

---
source: https://developer.apple.com/documentation/SwiftUI/TableColumnBuilder/buildIf(_:)
crawled: 2025-12-03T06:40:54Z
---

# buildIf(_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ TableColumnBuilder ](/documentation/swiftui/tablecolumnbuilder)

- [ buildIf(_:) ](/documentation/SwiftUI/TableColumnBuilder/buildIf(_:))

- [ TableColumnBuilder ](/documentation/swiftui/tablecolumnbuilder)

-  buildIf(_:) 

Type Method# buildIf(_:)

iOS 17.4+iPadOS 17.4+Mac Catalyst 17.4+macOS 14.4+visionOS 1.1+

```
static func buildIf<C>(_ content: C?) -> C? where RowValue == C.TableRowValue, C : TableColumnContent, C.TableColumnSortComparator == Never
```

Available when `RowValue` conforms to `Identifiable` and `Sort` conforms to `SortComparator`. Show all declarations