---
来源： https://developer.apple.com/documentation/SwiftUI/PointerStyle/image(_:hotSpot:)
抓取时间：2025-12-03T06:45:18Z
---

# image(_:hotSpot:)

**类型 方法**

使用给定的图像和热点初始化指针样式。

## 声明

```swift
static func image(_ image: Image, hotSpot: UnitPoint) -> PointerStyle
```

## 参数

- **image**：指针图像。
- **hotSpot**： 指针图像：图像上代表发生指针交互作用的位置的点。例如，箭头形状指针的热点就是箭头的尖端。

## 讨论

热点是指针必须位于屏幕元素上方才能产生点击效果的部分。

有关使用自定义指针的指导，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices]。

您可以使用[pointerStyle(_:)](../View/pointerStyle.zh-Hans.md)修饰符将此指针样式应用于单个视图或视图层次结构。

## 创建自定义指针样式

- **shape(_:eoFill:size:)**：使用给定的形状初始化指针样式。


---
source: https://developer.apple.com/documentation/SwiftUI/PointerStyle/image(_:hotSpot:)
crawled: 2025-12-03T06:45:18Z
---

# image(_:hotSpot:)

**Type Method**

Initializes a pointer style with a given image and hot spot.

## Declaration

```swift
static func image(_ image: Image, hotSpot: UnitPoint) -> PointerStyle
```

## Parameters

- **image**: The pointer image.
- **hotSpot**: The point on the image that represents the location from which the pointer interaction occurs. For example, the hot spot of an arrow-shaped pointer is the tip of the arrow.

## Discussion

The hot spot is the part of the pointer that must be positioned over an onscreen element for clicking to have an effect.

For guidance on using a custom pointer, refer to [doc://com.apple.documentation/design/Human-Interface-Guidelines/pointing-devices] in the Human Interface Guidelines.

You may apply this pointer style to a single view or a view hierarchy using the [pointerStyle(_:)](../View/pointerStyle.zh-Hans.md) modifier.

## Creating custom pointer styles

- **shape(_:eoFill:size:)**: Initializes a pointer style with a given shape.

