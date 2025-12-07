---
来源： https://developer.apple.com/documentation/SwiftUI/EmptyVisualEffect
抓取时间： 2025-12-02T17:37:28Z
---

# EmptyVisualEffect

**Structure**

基础视觉效果，您可以对其应用附加效果。

## 声明

```swift
struct EmptyVisualEffect
```

## 概览

`EmptyVisualEffect`不会改变所应用视图的外观。

## 创建空的视觉效果

- **init()**：创建一个新的空视觉效果。

## 根据几何图形应用特效

- **visualEffect(_:)**：将特效应用到该视图，同时通过几何体代理提供布局信息。
- **visualEffect3D(_:)**：为该视图应用特效，同时通过 3D 几何图形代理提供布局信息访问。
- **VisualEffect**：视觉特效可改变视图的视觉外观，而不会改变其祖先或后代。

## 符合

- 可动画
- 可发送
- 可发送元类型
- 视觉效果


---
source: https://developer.apple.com/documentation/SwiftUI/EmptyVisualEffect
crawled: 2025-12-02T17:37:28Z
---

# EmptyVisualEffect

**Structure**

The base visual effect that you apply additional effect to.

## Declaration

```swift
struct EmptyVisualEffect
```

## Overview

`EmptyVisualEffect` does not change the appearance of the view that it is applied to.

## Creating an empty visual effect

- **init()**: Creates a new empty visual effect.

## Applying effects based on geometry

- **visualEffect(_:)**: Applies effects to this view, while providing access to layout information through a geometry proxy.
- **visualEffect3D(_:)**: Applies effects to this view, while providing access to layout information through a 3D geometry proxy.
- **VisualEffect**: Visual Effects change the visual appearance of a view without changing its ancestors or descendents.

## Conforms To

- Animatable
- Sendable
- SendableMetatype
- VisualEffect

