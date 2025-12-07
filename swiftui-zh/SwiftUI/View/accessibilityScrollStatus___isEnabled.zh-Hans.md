--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityScrollStatus(_:isEnabled:)

抓取时间：2025-12-02T17:22:22Z

---

# accessibilityScrollStatus(_:isEnabled:)

**实例方法**

更改用户在此视图内滚动滚动视图时，辅助功能技术提供的提示信息。

## 声明

```swift
nonisolated func accessibilityScrollStatus(_ status: LocalizedStringResource, isEnabled: Bool = true) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
```

## 参数

- **status**：滚动视图的当前状态。

- **isEnabled**：如果为 true，则应用辅助功能滚动状态；否则，辅助功能滚动状态保持不变。

## 说明

使用此修饰符可提供滚动视图当前位置内容的描述。例如，您可以使用此修饰符在包含日历的视图中播报当前滚动到的月份。

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

默认情况下，VoiceOver 在滚动时会播报“第 X 页，共 Y 页”。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityScrollStatus(_:isEnabled:)
crawled: 2025-12-02T17:22:22Z
---

# accessibilityScrollStatus(_:isEnabled:)

**Instance Method**

Changes the announcement provided by accessibility technologies when a user scrolls a scroll view within this view.

## Declaration

```swift
nonisolated func accessibilityScrollStatus(_ status: LocalizedStringResource, isEnabled: Bool = true) -> ModifiedContent<Self, AccessibilityAttachmentModifier>
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

