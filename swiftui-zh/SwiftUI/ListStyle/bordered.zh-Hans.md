---
来源： https://developer.apple.com/documentation/SwiftUI/ListStyle/bordered
抓取时间： 2025-12-03T06:10:48Z
---

# 边框

**类型属性**

列表样式，用于描述带标准边框列表的行为和外观。

## 声明

```swift
static var bordered: BorderedListStyle { get }
```

## 讨论

有边框的列表应从其外部容器中嵌入，但没有嵌入样式的行或选区。

要自定义列表行是否应交替显示背景，请使用 [bordered(alternatesRowBackgrounds:)](bordered_alternatesRowBackgrounds.zh-Hans.md)。

## 获取内置列表样式

- **automatic**：描述平台默认行为和列表外观的列表样式。
- **carousel**：旋转木马列表样式。
- **elliptical**：列表样式：描述椭圆形列表的行为和外观的列表样式。
- **grouped**：描述椭圆形列表的行为和外观的列表样式：描述分组列表的行为和外观的列表样式。
- **inset**：列表样式，用于描述分组列表的行为和外观：描述插入列表的行为和外观的列表样式。
- **insetGrouped**：描述插入分组列表的行为和外观的列表样式。
- **plain**：描述普通列表的行为和外观的列表样式。
- **sidebar**：描述侧边栏列表行为和外观的列表样式。


---
source: https://developer.apple.com/documentation/SwiftUI/ListStyle/bordered
crawled: 2025-12-03T06:10:48Z
---

# bordered

**Type Property**

The list style that describes the behavior and appearance of a list with standard border.

## Declaration

```swift
static var bordered: BorderedListStyle { get }
```

## Discussion

Bordered lists are expected to be inset from their outer containers, but do not have inset style rows or selection.

To customize whether the rows of the list should alternate their backgrounds, use [bordered(alternatesRowBackgrounds:)](bordered_alternatesRowBackgrounds.zh-Hans.md).

## Getting built-in list styles

- **automatic**: The list style that describes a platform’s default behavior and appearance for a list.
- **carousel**: The carousel list style.
- **elliptical**: The list style that describes the behavior and appearance of an elliptical list.
- **grouped**: The list style that describes the behavior and appearance of a grouped list.
- **inset**: The list style that describes the behavior and appearance of an inset list.
- **insetGrouped**: The list style that describes the behavior and appearance of an inset grouped list.
- **plain**: The list style that describes the behavior and appearance of a plain list.
- **sidebar**: The list style that describes the behavior and appearance of a sidebar list.

