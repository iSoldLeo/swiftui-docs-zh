--- 来源：https://developer.apple.com/documentation/swiftui/edgeinsets

抓取时间：2025-12-04T13:36:07Z

---

# EdgeInsets

**Structure**

矩形边的内边距。

## 声明

```swift
@frozen struct EdgeInsets
```

## 获取边内边距

- **top**

- **bottom**

- **leading**

- **trailing**

## 创建边内边距

- **init()**

- **init(top:leading:bottom:trailing:)**

- **init(_:)**：从 `EdgeInsets3D` 创建 2D `EdgeInsets`，并舍弃其 `front` 和 `back` 的值。

## 实例方法

- **inset(by:edges:)**：返回一个内嵌值，该内嵌值已根据指定边的角点尺寸进行了调整。当指定边的两个角点内嵌值不同时，将使用较大的内嵌值。例如，如果指定了顶部边，则顶部内嵌值将根据顶部前导角和后导角内嵌值中较大的值进行调整。

## 访问边、区域和布局

- **Edge**：用于指示矩形一条边的枚举值。

- **Edge3D**：三维体素的边或面。

- **HorizontalEdge**：水平轴上的边。

- **VerticalEdge**：垂直轴上的边。

- **EdgeInsets3D**：三维体素各面的内嵌距离。

## 符合以下规范

- 可动画化

- 可按位复制

- 可复制

- 可等值化

- 可发送

- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/edgeinsets
crawled: 2025-12-04T13:36:07Z
---

# EdgeInsets

**Structure**

The inset distances for the sides of a rectangle.

## Declaration

```swift
@frozen struct EdgeInsets
```

## Getting edge insets

- **top**
- **bottom**
- **leading**
- **trailing**

## Creating an edge inset

- **init()**
- **init(top:leading:bottom:trailing:)**
- **init(_:)**: Creates a 2D `EdgeInsets` from an `EdgeInsets3D`, dropping its `front` and `back` values.

## Instance Methods

- **inset(by:edges:)**: Returns an inset that has been modified by the corner sizes in the specified edges. When two corner insets diverge in their values for the specified edge, the maximum inset value will be used. For example, when the top edge is specified, the top inset will be adjusted by the larger of the two heights from the top leading and trailing corner inset sizes.

## Accessing edges, regions, and layouts

- **Edge**: An enumeration to indicate one edge of a rectangle.
- **Edge3D**: An edge or face of a 3D volume.
- **HorizontalEdge**: An edge on the horizontal axis.
- **VerticalEdge**: An edge on the vertical axis.
- **EdgeInsets3D**: The inset distances for the faces of a 3D volume.

## Conforms To

- Animatable
- BitwiseCopyable
- Copyable
- Equatable
- Sendable
- SendableMetatype

