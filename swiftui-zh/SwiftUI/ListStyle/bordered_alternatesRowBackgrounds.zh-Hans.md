---
来源： https://developer.apple.com/documentation/SwiftUI/ListStyle/bordered(alternatesRowBackgrounds:)
抓取时间： 2025-12-03T06:10:54Z
---

# bordered(alternatesRowBackgrounds:)

**类型 方法**

描述带有标准边框的列表行为和外观的列表样式。

## 声明

```swift
static func bordered(alternatesRowBackgrounds: Bool) -> BorderedListStyle
```

## 参数

- **alternatesRowBackgrounds**：是否交替显示各行的背景，以便在视觉上区分它们。

## 讨论

有边框的列表应从其外部容器中嵌入，但没有嵌入样式的行或选区。

## 过时样式

- **inset(alternatesRowBackgrounds:)**：列表样式，用于描述具有可选交替行背景的嵌入式列表的行为和外观。


---
source: https://developer.apple.com/documentation/SwiftUI/ListStyle/bordered(alternatesRowBackgrounds:)
crawled: 2025-12-03T06:10:54Z
---

# bordered(alternatesRowBackgrounds:)

**Type Method**

The list style that describes the behavior and appearance of a list with standard border.

## Declaration

```swift
static func bordered(alternatesRowBackgrounds: Bool) -> BorderedListStyle
```

## Parameters

- **alternatesRowBackgrounds**: Whether the rows should alternate their backgrounds to help visually distinguish them from each other.

## Discussion

Bordered lists are expected to be inset from their outer containers, but do not have inset style rows or selection.

## Deprecated styles

- **inset(alternatesRowBackgrounds:)**: The list style that describes the behavior and appearance of an inset list with optional alternating row backgrounds.

