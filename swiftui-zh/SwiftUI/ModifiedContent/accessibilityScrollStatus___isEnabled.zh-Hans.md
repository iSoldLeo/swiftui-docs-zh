---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityScrollStatus(_:isEnabled:)
抓取时间： 2025-11-30T21:32:02Z
---

# accessibilityScrollStatus(_:isEnabled:)

**实例方法**

当用户滚动此视图中的滚动视图时，更改辅助功能技术提供的公告。

## 声明

```swift
nonisolated func accessibilityScrollStatus(_ status: LocalizedStringResource, isEnabled: Bool = true) -> ModifiedContent<Content, Modifier>
```

## 参数

- **status**：滚动视图的当前状态。
- **isEnabled**：

## 讨论

使用此修改器可对滚动视图中当前位置的内容进行描述。例如，在包含日历的视图中，可以使用此修改器来显示当前滚动到的月份。

```swift
@State private var position = ScrollPosition(idType: Month.ID.self)

ScrollView {
    LazyVStack {
        ForEach(months) { months in
            MonthView(month: months)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition($position)
.accessibilityScrollStatus("\(months.name(position.viewID)) \(year)")
```

默认情况下，VoiceOver 会在滚动时播报 "Page X of Y"。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibilityScrollStatus(_:isEnabled:)
crawled: 2025-11-30T21:32:02Z
---

# accessibilityScrollStatus(_:isEnabled:)

**Instance Method**

Changes the announcement provided by accessibility technologies when a user scrolls a scroll view within this view.

## Declaration

```swift
nonisolated func accessibilityScrollStatus(_ status: LocalizedStringResource, isEnabled: Bool = true) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **status**: The current status of the scroll view.
- **isEnabled**: If true the accessibility scroll status is applied; otherwise the accessibility scroll status is unchanged.

## Discussion

Use this modifier to provide a description of the content at the current position in the scroll view. For example, you could use this modifier to announce the current month being scrolled to in a view that contains a calendar.

```swift
@State private var position = ScrollPosition(idType: Month.ID.self)

ScrollView {
    LazyVStack {
        ForEach(months) { months in
            MonthView(month: months)
        }
    }
    .scrollTargetLayout()
}
.scrollPosition($position)
.accessibilityScrollStatus("\(months.name(position.viewID)) \(year)")
```

By default, VoiceOver announces “Page X of Y” while scrolling.

