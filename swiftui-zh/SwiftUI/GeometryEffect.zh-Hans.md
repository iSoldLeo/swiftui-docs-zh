---
来源： https://developer.apple.com/documentation/SwiftUI/GeometryEffect
抓取时间： 2025-12-02T17:34:17Z
---

# 几何效应

**Protocol**

一种可以改变视图视觉外观的效果，主要是在不改变其祖先或后代的情况下。

## 声明

```swift
protocol GeometryEffect : Animatable, ViewModifier, _RemoveGlobalActorIsolation where Self.Body == Never
```

## 概览

该特效对视图的祖先和后代所做的唯一更改就是改变它们之间的坐标变换。

## 应用特效

- **effectValue(size:)**：返回效果的当前值。
- **ignoredByLayout()**：返回与此效果产生相同几何变换的效果，但只在渲染视图时应用变换。

## 同步几何体

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**：使用您提供的标识符和命名空间定义一组具有同步几何图形的视图。
- **MatchedGeometryProperties**：一组视图属性，可使用`View.matchedGeometryEffect()` 函数在视图之间同步。
- **Namespace**：动态属性类型，允许访问由包含该属性的对象（如视图）的持久标识所定义的命名空间。
- **geometryGroup()**：将视图的几何形状（如位置和大小）与其父视图隔离。

## 继承自

- 动画
- 视图修改器


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryEffect
crawled: 2025-12-02T17:34:17Z
---

# GeometryEffect

**Protocol**

An effect that changes the visual appearance of a view, largely without changing its ancestors or descendants.

## Declaration

```swift
protocol GeometryEffect : Animatable, ViewModifier, _RemoveGlobalActorIsolation where Self.Body == Never
```

## Overview

The only change the effect makes to the view’s ancestors and descendants is to change the coordinate transform to and from them.

## Applying effects

- **effectValue(size:)**: Returns the current value of the effect.
- **ignoredByLayout()**: Returns an effect that produces the same geometry transform as this effect, but only applies the transform while rendering its view.

## Synchronizing geometries

- **matchedGeometryEffect(id:in:properties:anchor:isSource:)**: Defines a group of views with synchronized geometry using an identifier and namespace that you provide.
- **MatchedGeometryProperties**: A set of view properties that may be synchronized between views using the `View.matchedGeometryEffect()` function.
- **Namespace**: A dynamic property type that allows access to a namespace defined by the persistent identity of the object containing the property (e.g. a view).
- **geometryGroup()**: Isolates the geometry (e.g. position and size) of the view from its parent view.

## Inherits From

- Animatable
- ViewModifier

