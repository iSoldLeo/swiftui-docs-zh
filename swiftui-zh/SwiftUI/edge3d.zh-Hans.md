---
来源： https://developer.apple.com/documentation/swiftui/edge3d
抓取时间： 2025-12-04T13:34:11Z
---

# Edge3D

**Enumeration**

三维体的边缘或面。

## 声明

```swift
@frozen enum Edge3D
```

## 获取边缘

- **Edge3D.top**
- **Edge3D.bottom**
- **Edge3D.leading**
- **Edge3D.trailing**
- **Edge3D.front**
- **Edge3D.back**

## 创建一条边

- **init(_:)**

## 访问边集

- **Edge3D.Set**：高效的 3D 边集。

## 访问边缘、区域和布局

- **Edge**：枚举表示矩形的一条边。
- **HorizontalEdge**：水平轴上的一条边。
- **VerticalEdge**：垂直轴上的一条边：垂直轴上的一条边。
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
source: https://developer.apple.com/documentation/swiftui/edge3d
crawled: 2025-12-04T13:34:11Z
---

# Edge3D

**Enumeration**

An edge or face of a 3D volume.

## Declaration

```swift
@frozen enum Edge3D
```

## Getting the edges

- **Edge3D.top**
- **Edge3D.bottom**
- **Edge3D.leading**
- **Edge3D.trailing**
- **Edge3D.front**
- **Edge3D.back**

## Creating an edge

- **init(_:)**

## Accessing sets of edges

- **Edge3D.Set**: An efficient set of 3D edges.

## Accessing edges, regions, and layouts

- **Edge**: An enumeration to indicate one edge of a rectangle.
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

