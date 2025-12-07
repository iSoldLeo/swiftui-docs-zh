--- 来源：https://developer.apple.com/documentation/SwiftUI/DynamicTypeSize
抓取时间：2025-12-02T17:34:47Z

---

# DynamicTypeSize

**Enumeration**

动态字体大小，用于指定可缩放内容的大小。

## 声明

```swift
enum DynamicTypeSize
```

## 概述

更多信息，请参阅人机界面指南中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/typography]。

## 获取字体大小

- **DynamicTypeSize.xSmall**：超小尺寸。

- **DynamicTypeSize.small**：小尺寸。

- **DynamicTypeSize.medium**：中等尺寸。

- **DynamicTypeSize.large**：大尺寸。

- **DynamicTypeSize.xLarge**：特大号。

- **DynamicTypeSize.xxLarge**：超大号。

- **DynamicTypeSize.xxxLarge**：超超大号。

## 获取辅助功能尺寸

- **DynamicTypeSize.accessibility1**：第一个辅助功能尺寸。

- **DynamicTypeSize.accessibility2**：第二个辅助功能尺寸。

- **DynamicTypeSize.accessibility3**：第三个辅助功能尺寸。

- **DynamicTypeSize.accessibility4**：第四个辅助功能尺寸。

- **DynamicTypeSize.accessibility5**：第五个辅助功能尺寸。

- **isAccessibilitySize**：一个布尔值，指示该尺寸是否与辅助功能相关。

## 创建字体大小

- **init(_:)**：根据其对应的 `UIContentSizeCategory` 字体大小创建动态字体大小。

## 调整文本大小

- **textScale(_:isEnabled:)**：对视图中的文本应用文本缩放。

- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。

- **dynamicTypeSize**：当前的动态字体大小。

- **ScaledMetric**：缩放数值的动态属性。

- **TextVariantPreference**：用于控制文本视图大小变体的协议。

- **FixedTextVariant**：默认文本变体首选项，选择可用的最大变体。

- **SizeDependentTextVariant**：大小相关的变体偏好设置允许文本在选择要显示的变体时考虑可用空间。

## 符合以下标准

- CaseIterable

- Comparable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/DynamicTypeSize
crawled: 2025-12-02T17:34:47Z
---

# DynamicTypeSize

**Enumeration**

A Dynamic Type size, which specifies how large scalable content should be.

## Declaration

```swift
enum DynamicTypeSize
```

## Overview

For more information, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/typography] in the Human Interface Guidelines.

## Getting type sizes

- **DynamicTypeSize.xSmall**: An extra small size.
- **DynamicTypeSize.small**: A small size.
- **DynamicTypeSize.medium**: A medium size.
- **DynamicTypeSize.large**: A large size.
- **DynamicTypeSize.xLarge**: An extra large size.
- **DynamicTypeSize.xxLarge**: An extra extra large size.
- **DynamicTypeSize.xxxLarge**: An extra extra extra large size.

## Getting accessibility type sizes

- **DynamicTypeSize.accessibility1**: The first accessibility size.
- **DynamicTypeSize.accessibility2**: The second accessibility size.
- **DynamicTypeSize.accessibility3**: The third accessibility size.
- **DynamicTypeSize.accessibility4**: The fourth accessibility size.
- **DynamicTypeSize.accessibility5**: The fifth accessibility size.
- **isAccessibilitySize**: A Boolean value indicating whether the size is one that is associated with accessibility.

## Creating a type size

- **init(_:)**: Create a Dynamic Type size from its `UIContentSizeCategory` equivalent.

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **dynamicTypeSize**: The current Dynamic Type size.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

## Conforms To

- CaseIterable
- Comparable
- Equatable
- Hashable
- Sendable
- SendableMetatype

