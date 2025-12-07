---
来源： https://developer.apple.com/documentation/SwiftUI/LegibilityWeight
抓取时间： 2025-12-02T17:43:43Z
---

# 可读性权重

**Enumeration**

辅助功能粗体字用户设置选项。

## 声明

```swift
enum LegibilityWeight
```

## 概览

在 iOS 16、tvOS 16 或 watchOS 9.0 之前，应用程序无法覆盖用户的选择。

## 获取权重

- **LegibilityWeight.regular**：使用常规字体权重（无辅助功能粗体）。
- **LegibilityWeight.bold**：使用较重的字体（强制无障碍粗体）。

## 创建权重

- **init(_:)**：从等效的 UILegibilityWeight 创建可读性权重。

## 提高可读性

- **accessibilityShowButtonShapes**：是否启用了显示按钮形状的系统偏好设置。
- **accessibilityReduceTransparency**：是否启用了 "降低透明度 "系统偏好设置。
- **legibilityWeight**：应用于文本的字体权重。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/LegibilityWeight
crawled: 2025-12-02T17:43:43Z
---

# LegibilityWeight

**Enumeration**

The Accessibility Bold Text user setting options.

## Declaration

```swift
enum LegibilityWeight
```

## Overview

The app can’t override the user’s choice before iOS 16, tvOS 16 or watchOS 9.0.

## Getting weights

- **LegibilityWeight.regular**: Use regular font weight (no Accessibility Bold).
- **LegibilityWeight.bold**: Use heavier font weight (force Accessibility Bold).

## Creating a weight

- **init(_:)**: Creates a legibility weight from its UILegibilityWeight equivalent.

## Improving legibility

- **accessibilityShowButtonShapes**: Whether the system preference for Show Button Shapes is enabled.
- **accessibilityReduceTransparency**: Whether the system preference for Reduce Transparency is enabled.
- **legibilityWeight**: The font weight to apply to text.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

