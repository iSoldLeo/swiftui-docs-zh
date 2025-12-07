---
来源： https://developer.apple.com/documentation/swiftui/color/resolved
抓取时间： 2025-12-04T11:33:59Z
---

# 颜色.已解决

**Structure**

一个具体的颜色值。

## 声明

```swift
@frozen struct Resolved
```

## 概览

`Color.Resolved` 是一组 RGBA 值，表示可以显示的颜色。这些值使用扩展范围存储在线性 sRGB 色彩空间中。这是一种低级类型，大多数颜色都由`Color` 类型表示。



## 初始化器

- **init(colorSpace:red:green:blue:opacity:)**：根据红、绿、蓝分量值创建解析颜色。

## 实例属性

- **blue**：在 sRGB 色彩空间中颜色的蓝色含量。
- **cgColor**：颜色的 Core Graphics 表示。
- **green**：在 sRGB 色彩空间中颜色的绿色含量。
- **linearBlue**：在 sRGB 线性色彩空间中颜色的蓝量。
- **linearGreen**：在 sRGB 线性色彩空间中颜色的绿度。
- **linearRed**：在 sRGB 线性色彩空间中颜色的红色分量。
- **opacity**：颜色的不透明度，取值范围为 `0` 至 `1`。
- **red**：在 sRGB 色彩空间中颜色的红色含量。

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
source: https://developer.apple.com/documentation/swiftui/color/resolved
crawled: 2025-12-04T11:33:59Z
---

# Color.Resolved

**Structure**

A concrete color value.

## Declaration

```swift
@frozen struct Resolved
```

## Overview

`Color.Resolved` is a set of RGBA values that represent a color that can be shown. The values are stored in the Linear sRGB color space, using extended range. This is a low-level type, most colors are represented by the `Color` type.



## Initializers

- **init(colorSpace:red:green:blue:opacity:)**: Creates a resolved color from red, green, and blue component values.

## Instance Properties

- **blue**: The amount of blue in the color in the sRGB color space.
- **cgColor**: A Core Graphics representation of the color.
- **green**: The amount of green in the color in the sRGB color space.
- **linearBlue**: The amount of blue in the color in the sRGB linear color space.
- **linearGreen**: The amount of green in the color in the sRGB linear color space.
- **linearRed**: The amount of red in the color in the sRGB linear color space.
- **opacity**: The degree of opacity in the color, given in the range `0` to `1`.
- **red**: The amount of red in the color in the sRGB color space.

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

