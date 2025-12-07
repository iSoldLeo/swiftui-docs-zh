---
来源：https://developer.apple.com/documentation/SwiftUI/PointerStyle/shape(_:eoFill:size:)
抓取时间： 2025-12-01T11:34:33Z
---

# shape(_:eoFill:size:)

**类型方法**

用给定的形状初始化指针样式。

## 声明

```swift
static func shape(_ shape: some Shape, eoFill: Bool = false, size: CGSize) -> PointerStyle
```

## 参数

- **shape**：指针形状。
- **eoFill**：布尔值，表示是否使用偶数绕组数规则解释形状。
- **size**：指针形状的大小。

## 讨论

有关使用自定义指针的指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices]。

您可以使用[pointerStyle(_:)](../View/pointerStyle.zh-Hans.md)修饰符将这种指针样式应用于单个视图或视图层次结构。

## 创建自定义指针样式

- **image(_:hotSpot:)**：使用给定的图像和热点初始化指针样式。


---
source: https://developer.apple.com/documentation/SwiftUI/PointerStyle/shape(_:eoFill:size:)
crawled: 2025-12-01T11:34:33Z
---

# shape(_:eoFill:size:)

**Type Method**

Initializes a pointer style with a given shape.

## Declaration

```swift
static func shape(_ shape: some Shape, eoFill: Bool = false, size: CGSize) -> PointerStyle
```

## Parameters

- **shape**: The pointer shape.
- **eoFill**: A Boolean that indicates whether the shape is interpreted with the even-odd winding number rule.
- **size**: The size of the pointer shape.

## Discussion

For guidance on using a custom pointer, refer to [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices] in the Human Interface Guidelines.

You may apply this pointer style to a single view or a view hierarchy using the [pointerStyle(_:)](../View/pointerStyle.zh-Hans.md) modifier.

## Creating custom pointer styles

- **image(_:hotSpot:)**: Initializes a pointer style with a given image and hot spot.

