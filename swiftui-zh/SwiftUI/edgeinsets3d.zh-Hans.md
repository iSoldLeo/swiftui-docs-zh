---
来源： https://developer.apple.com/documentation/swiftui/edgeinsets3d
抓取时间： 2025-12-02T17:53:24Z
---

# EdgeInsets3D

**Structure**

三维实体面的嵌入距离。

## 声明

```swift
@frozen struct EdgeInsets3D
```

## 获取边缘嵌入

- **top**：三维体顶面的嵌入距离。
- **bottom**：三维实体底面的嵌入距离。
- **leading**：沿三维实体前端面的嵌入距离。
- **trailing**：三维实体顶部尾部的嵌入距离。
- **front**：三维实体前端顶部的嵌入距离。
- **back**：三维立体图像背面顶部的嵌入距离。

## 创建边缘嵌入

- **init(horizontal:vertical:depth:)**：创建一个`EdgeInsets3D`值，每个轴都有相应的值。
- **init(top:leading:bottom:trailing:front:back:)**：创建`EdgeInsets3D` 值，为每个面提供值。

## 访问边、区域和布局

- **Edge**：一个枚举，用于表示矩形的一条边。
- **Edge3D**：三维体的一条边或一个面。
- **HorizontalEdge**：水平轴上的边缘。
- **VerticalEdge**：垂直轴上的一条边。
- **EdgeInsets**：垂直轴上的一条边：矩形边的嵌入距离。

## 符合

- 可动画
- 比特可复制
- 可复制
- 等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/edgeinsets3d
crawled: 2025-12-02T17:53:24Z
---

# EdgeInsets3D

**Structure**

The inset distances for the faces of a 3D volume.

## Declaration

```swift
@frozen struct EdgeInsets3D
```

## Getting edge insets

- **top**: The inset distance along the top face of a 3D volume.
- **bottom**: The inset distance along the bottom face of a 3D volume.
- **leading**: The inset distance along the leading face of a 3D volume.
- **trailing**: The inset distance along the top trailing of a 3D volume.
- **front**: The inset distance along the top front of a 3D volume.
- **back**: The inset distance along the top back of a 3D volume.

## Creating an edge inset

- **init(horizontal:vertical:depth:)**: Creates an `EdgeInsets3D` value with values provided for each axis.
- **init(top:leading:bottom:trailing:front:back:)**: Creates an `EdgeInsets3D` value with values provided for each face.

## Accessing edges, regions, and layouts

- **Edge**: An enumeration to indicate one edge of a rectangle.
- **Edge3D**: An edge or face of a 3D volume.
- **HorizontalEdge**: An edge on the horizontal axis.
- **VerticalEdge**: An edge on the vertical axis.
- **EdgeInsets**: The inset distances for the sides of a rectangle.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

