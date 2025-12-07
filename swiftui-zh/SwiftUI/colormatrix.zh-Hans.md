--- 来源：https://developer.apple.com/documentation/swiftui/colormatrix
抓取时间：2025-12-04T13:24:37Z

---

# ColorMatrix

**Structure**

用于 RGBA 颜色变换的矩阵。

## 声明

```swift
@frozen struct ColorMatrix
```

## 概述

该矩阵有五列，每列包含红色、绿色、蓝色和 alpha 分量。您可以使用该矩阵执行诸如使用 [colorMatrix(_:)](GraphicsContext/Filter/colorMatrix.zh-Hans.md) 方法为 [GraphicsContext](GraphicsContext.zh-Hans.md) 创建颜色变换之类的任务。

## 创建单位矩阵

- **init()**：创建单位矩阵。

## 第一列

- **r1**
- **g1**
- **b1**
- **a1**

## 第二列

- **r2**
- **g2**
- **b2**
- **a2**

## 第三列

- **r3**
- **g3**
- **b3**
- **a3**

## 第四列

- **r4**
- **g4**
- **b4**

- **a4**

## 第五列

- **r5**

- **g5**

- **b5**

- **a5**

## 应用模糊和阴影

- **blur(radius:opaque:)**：对此视图应用高斯模糊。

- **shadow(color:radius:x:y:)**：为此视图添加阴影。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 等值 (Equatable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/swiftui/colormatrix
crawled: 2025-12-04T13:24:37Z
---

# ColorMatrix

**Structure**

A matrix to use in an RGBA color transformation.

## Declaration

```swift
@frozen struct ColorMatrix
```

## Overview

The matrix has five columns, each with a red, green, blue, and alpha component. You can use the matrix for tasks like creating a color transformation [Filter](GraphicsContext/Filter.zh-Hans.md) for a [GraphicsContext](GraphicsContext.zh-Hans.md) using the [colorMatrix(_:)](GraphicsContext/Filter/colorMatrix.zh-Hans.md) method.

## Creating an identity matrix

- **init()**: Creates the identity matrix.

## First column

- **r1**
- **g1**
- **b1**
- **a1**

## Second column

- **r2**
- **g2**
- **b2**
- **a2**

## Third column

- **r3**
- **g3**
- **b3**
- **a3**

## Fourth column

- **r4**
- **g4**
- **b4**
- **a4**

## Fifth column

- **r5**
- **g5**
- **b5**
- **a5**

## Applying blur and shadows

- **blur(radius:opaque:)**: Applies a Gaussian blur to this view.
- **shadow(color:radius:x:y:)**: Adds a shadow to this view.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

