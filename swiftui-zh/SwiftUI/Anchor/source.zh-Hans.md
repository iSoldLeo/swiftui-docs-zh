--- 来源：https://developer.apple.com/documentation/swiftui/anchor/source
抓取时间：2025-12-05T22:25:45Z

---

# Anchor.Source

**Structure**

一个类型擦除的几何值，用于生成给定类型的锚定值。

## 声明

```swift
@frozen struct Source
```

## 概述

SwiftUI 通过偏好设置键在视图树中传递锚定的几何值。然后，它使用 [GeometryProxy](../GeometryProxy.zh-Hans.md) 值将它们转换回局部坐标空间。

## 获取点锚点源

- **point(_:)**

- **unitPoint(_:)**

## 获取矩形锚点源

- **rect(_:)**：返回当前视图中由 `r` 定义的锚点源矩形。

- **bounds**：返回当前视图的整个边界矩形。

## 获取顶部锚点源

- **topLeading**

- **top**

- **topTrailing**

## 获取中间锚点源

- **leading**

- **center**

- **trailing**

## 获取底部锚点源

- **bottomTrailing**

- **bottom**

- **bottomLeading**

## 创建锚点源

- **init(_:)**

## 类型属性

- **bounds3D**：锚点源矩形，定义为当前元素的整个边界矩形。

- **center**

- **center3D**

## 类型方法

- **point3D(_:)**

- **rect3D(_:)**：返回由 `r` 在当前元素中定义的锚点源矩形。

- **unitPoint3D(_:)**

## 符合以下协议

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/anchor/source
crawled: 2025-12-05T22:25:45Z
---

# Anchor.Source

**Structure**

A type-erased geometry value that produces an anchored value of a given type.

## Declaration

```swift
@frozen struct Source
```

## Overview

SwiftUI passes anchored geometry values around the view tree via preference keys. It then converts them back into the local coordinate space using a [GeometryProxy](../GeometryProxy.zh-Hans.md) value.

## Getting point anchor sources

- **point(_:)**
- **unitPoint(_:)**

## Getting rectangle anchor sources

- **rect(_:)**: Returns an anchor source rect defined by `r` in the current view.
- **bounds**: An anchor source rect defined as the entire bounding rect of the current view.

## Getting top anchor sources

- **topLeading**
- **top**
- **topTrailing**

## Getting middle anchor sources

- **leading**
- **center**
- **trailing**

## Getting bottom anchor sources

- **bottomTrailing**
- **bottom**
- **bottomLeading**

## Creating an anchor source

- **init(_:)**

## Type Properties

- **bounds3D**: An anchor source rect defined as the entire bounding rect of the current element.
- **center**
- **center3D**

## Type Methods

- **point3D(_:)**
- **rect3D(_:)**: Returns an anchor source rect defined by `r` in the current element.
- **unitPoint3D(_:)**

## Conforms To

- Sendable
- SendableMetatype

