---
来源： https://developer.apple.com/documentation/SwiftUI/NamedCoordinateSpace
抓取时间： 2025-12-03T06:33:52Z
---

# 命名坐标空间

**Structure**

已命名的坐标空间。

## 声明

```swift
struct NamedCoordinateSpace
```

## 概览

使用`coordinateSpace(_:)`修饰符为父视图的局部坐标空间指定名称。子视图可以使用 `.named(_:)` 引用该坐标空间。

## 支持类型

- **GlobalCoordinateSpace**：位于视图层次结构根部的全局坐标空间。
- **LocalCoordinateSpace**：当前视图的局部坐标空间。

## 符合

- 坐标空间协议
- 等价


---
source: https://developer.apple.com/documentation/SwiftUI/NamedCoordinateSpace
crawled: 2025-12-03T06:33:52Z
---

# NamedCoordinateSpace

**Structure**

A named coordinate space.

## Declaration

```swift
struct NamedCoordinateSpace
```

## Overview

Use the `coordinateSpace(_:)` modifier to assign a name to the local coordinate space of a  parent view. Child views can then refer to that coordinate space using `.named(_:)`.

## Supporting types

- **GlobalCoordinateSpace**: The global coordinate space at the root of the view hierarchy.
- **LocalCoordinateSpace**: The local coordinate space of the current view.

## Conforms To

- CoordinateSpaceProtocol
- Equatable

