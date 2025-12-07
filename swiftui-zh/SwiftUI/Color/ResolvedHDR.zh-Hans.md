---
来源： https://developer.apple.com/documentation/SwiftUI/Color/ResolvedHDR
抓取时间： 2025-12-03T05:39:57Z
---

# Color.ResolvedHDR

**Structure**

具体的色彩值，包括 HDR 净空信息。

## 声明

```swift
@frozen struct ResolvedHDR
```

## 概览

`Color.ResolvedHDR`是一组 RGBA 值，表示可以显示的颜色。颜色分量存储在扩展的 sRGB 色彩空间中，并可能包含一个 "余量 "值，用于描述在不同动态范围的显示器上如何呈现颜色。这是一种低级类型，大多数颜色都由`Color` 类型表示。



## 创建具体的颜色值

- **init(_:headroom:)**：初始化一个新的已解析颜色值。

## 获取颜色属性

- **red**：颜色在扩展 sRGB 色彩空间中的红色含量。
- **green**：扩展 sRGB 色彩空间中颜色的绿度。
- **blue**：扩展 sRGB 色彩空间中颜色的蓝量。
- **linearRed**：在具有线性伽玛的扩展 sRGB 色彩空间变体中颜色的红色量。
- **linearGreen**：在具有线性伽玛的扩展 sRGB 色彩空间变体中颜色的绿度。
- **linearBlue**：在具有线性伽玛的扩展 sRGB 色彩空间变体中颜色的蓝量。
- **opacity**：颜色的不透明度，范围为 `0` 至 `1`。
- **headroom**：颜色的内容净空。

## 处理高动态范围 (HDR) 色彩

- **resolveHDR(in:)**：在给定一组环境值的情况下，将该颜色评估为具有内容余量的解析颜色。

## 符合

- 可动画
- 比特可复制
- 可复制
- 自定义字符串可转换
- 可解码
- 可编码
- 等价
- 可散列
- 可发送
- 可发送元类型
- 形状样式


---
source: https://developer.apple.com/documentation/SwiftUI/Color/ResolvedHDR
crawled: 2025-12-03T05:39:57Z
---

# Color.ResolvedHDR

**Structure**

A concrete color value, including HDR headroom information.

## Declaration

```swift
@frozen struct ResolvedHDR
```

## Overview

`Color.ResolvedHDR` is a set of RGBA values that represent a color that can be shown. The color components are stored in the extended sRGB color space and may contain a “headroom” value describing how the color is rendered for displays with different dynamic ranges. This is a low-level type, most colors are represented by the `Color` type.



## Creating a concrete color value

- **init(_:headroom:)**: Initializes a new resolved color value.

## Getting color properties

- **red**: The amount of red in the color in the extended sRGB color space.
- **green**: The amount of green in the color in the extended sRGB color space.
- **blue**: The amount of blue in the color in the extended sRGB color space.
- **linearRed**: The amount of red in the color in the extended sRGB color space variant with linear gamma.
- **linearGreen**: The amount of green in the color in the extended sRGB color space variant with linear gamma.
- **linearBlue**: The amount of blue in the color in the extended sRGB color space variant with linear gamma.
- **opacity**: The opacity of the color, in the range `0` to `1`.
- **headroom**: The content headroom of the color.

## Working with high dynamic range (HDR) colors

- **resolveHDR(in:)**: Evaluates this color to a resolved color with content headroom, given a set of environment values.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- CustomStringConvertible
- Decodable
- Encodable
- Equatable
- Hashable
- Sendable
- SendableMetatype
- ShapeStyle

