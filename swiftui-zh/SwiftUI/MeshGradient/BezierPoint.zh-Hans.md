--- 来源：https://developer.apple.com/documentation/SwiftUI/MeshGradient/BezierPoint

抓取时间：2025-12-03T05:42:59Z

---

# MeshGradient.BezierPoint

**Structure**

渐变网格中的一个位置，以及围绕它的四个贝塞尔曲线控制点。

## 声明

```swift
@frozen struct BezierPoint
```

## 初始化器

- **init(position:leadingControlPoint:topControlPoint:trailingControlPoint:bottomControlPoint:)**：创建一个新的顶点。

## 实例属性

- **bottomControlPoint**：顶点底部边缘的贝塞尔曲线控制点。

- **leadingControlPoint**：顶点前缘的贝塞尔曲线控制点。

- **position**：顶点的位置。

- **topControlPoint**：顶点顶边的贝塞尔控制点。

- **trailingControlPoint**：顶点尾边的贝塞尔控制点。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 可等值 (Equatable)

- 可发送 (Sendable)

- 可发送元类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/SwiftUI/MeshGradient/BezierPoint
crawled: 2025-12-03T05:42:59Z
---

# MeshGradient.BezierPoint

**Structure**

One location in a gradient mesh, along with the four Bezier control points surrounding it.

## Declaration

```swift
@frozen struct BezierPoint
```

## Initializers

- **init(position:leadingControlPoint:topControlPoint:trailingControlPoint:bottomControlPoint:)**: Creates a new vertex.

## Instance Properties

- **bottomControlPoint**: The Bezier control point of the vertex’s bottom edge.
- **leadingControlPoint**: The Bezier control point of the vertex’s leading edge.
- **position**: The position of the vertex.
- **topControlPoint**: The Bezier control point of the vertex’s top edge.
- **trailingControlPoint**: The Bezier control point of the vertex’s trailing edge.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

