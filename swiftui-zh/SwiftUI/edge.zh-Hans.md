---
来源： https://developer.apple.com/documentation/swiftui/edge
抓取时间： 2025-12-04T13:32:34Z
---

# 边缘

**Enumeration**

表示矩形的一条边的枚举。

## 声明

```swift
@frozen enum Edge
```

## 获取边缘

- **Edge.top**
- **Edge.bottom**
- **Edge.leading**
- **Edge.trailing**

## 创建一条边

- **init(_:)**：尽可能将 3D 边缘转换为 2D 边缘。

## 访问边集

- **Edge.Set**：一个有效的边集。

## 枚举

- **Edge.Corner**：表示矩形一角的枚举。

## 访问边缘、区域和布局

- **Edge3D**：三维体的边缘或面。
- **HorizontalEdge**：水平轴上的边缘。
- **VerticalEdge**：垂直轴上的一条边。
- **EdgeInsets**：矩形边的嵌入距离。
- **EdgeInsets3D**：三维体的面的嵌入距离。

## 符合

- 比特可复制
- CaseIterable
- 可复制
- 等价
- Hashable
- 原始可表示
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/edge
crawled: 2025-12-04T13:32:34Z
---

# Edge

**Enumeration**

An enumeration to indicate one edge of a rectangle.

## Declaration

```swift
@frozen enum Edge
```

## Getting the edges

- **Edge.top**
- **Edge.bottom**
- **Edge.leading**
- **Edge.trailing**

## Creating an edge

- **init(_:)**: Converts a 3D edge to a 2D edge, if possible.

## Accessing sets of edges

- **Edge.Set**: An efficient set of edges.

## Enumerations

- **Edge.Corner**: An enumeration to indicate one corner of a rectangle.

## Accessing edges, regions, and layouts

- **Edge3D**: An edge or face of a 3D volume.
- **HorizontalEdge**: An edge on the horizontal axis.
- **VerticalEdge**: An edge on the vertical axis.
- **EdgeInsets**: The inset distances for the sides of a rectangle.
- **EdgeInsets3D**: The inset distances for the faces of a 3D volume.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

