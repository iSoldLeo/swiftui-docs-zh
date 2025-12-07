---
来源： https://developer.apple.com/documentation/SwiftUI/ListStyle/insetGrouped
抓取时间： 2025-12-03T06:10:52Z
---

# insetGrouped

**类型属性**

描述插入分组列表的行为和外观的列表样式。

## 声明

```swift
static var insetGrouped: InsetGroupedListStyle { get }
```

## 讨论

在 iOS 上，嵌入式分组列表样式会显示一种连续的背景色，这种背景色从部分标题开始，围绕着部分中列表项的两侧，一直延伸到部分页脚。与[inset](inset.zh-Hans.md) 或 [grouped](grouped.zh-Hans.md)样式相比，这种样式能在更大程度上对项目进行视觉分组。

## 获取内置列表样式

- **automatic**：列表样式，用于描述平台默认的列表行为和外观。
- **bordered**：列表样式，用于描述带有标准边框的列表的行为和外观。
- **carousel**：旋转木马列表样式。
- **elliptical**：旋转木马列表样式：描述椭圆形列表的行为和外观的列表样式。
- **grouped**：描述椭圆形列表的行为和外观的列表样式：描述分组列表的行为和外观的列表样式。
- **inset**：列表样式，用于描述分组列表的行为和外观：描述插入列表的行为和外观的列表样式。
- **plain**：描述普通列表的行为和外观的列表样式。
- **sidebar**：描述侧边栏列表行为和外观的列表样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ListStyle/insetGrouped
crawled: 2025-12-03T06:10:52Z
---

# insetGrouped

**Type Property**

The list style that describes the behavior and appearance of an inset grouped list.

## Declaration

```swift
static var insetGrouped: InsetGroupedListStyle { get }
```

## Discussion

On iOS, the inset grouped list style displays a continuous background color that extends from the section header, around both sides of list items in the section, and down to the section footer. This visually groups the items to a greater degree than either the [inset](inset.zh-Hans.md) or [grouped](grouped.zh-Hans.md) styles do.

## Getting built-in list styles

- **automatic**: The list style that describes a platform’s default behavior and appearance for a list.
- **bordered**: The list style that describes the behavior and appearance of a list with standard border.
- **carousel**: The carousel list style.
- **elliptical**: The list style that describes the behavior and appearance of an elliptical list.
- **grouped**: The list style that describes the behavior and appearance of a grouped list.
- **inset**: The list style that describes the behavior and appearance of an inset list.
- **plain**: The list style that describes the behavior and appearance of a plain list.
- **sidebar**: The list style that describes the behavior and appearance of a sidebar list.

