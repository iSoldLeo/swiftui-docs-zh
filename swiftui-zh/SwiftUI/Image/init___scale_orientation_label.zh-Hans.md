---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(_:scale:orientation:label:)
抓取时间：2025-12-01T09:18:18Z
---

# init(_:scale:orientation:label:)

**Initializer**

根据 Core Graphics 图像实例创建带标签的图像，用作控件的内容。

## 声明

```swift
init(_ cgImage: CGImage, scale: CGFloat, orientation: Image.Orientation = .up, label: Text)
```

## 参数

- **cgImage**：基础图形图像。
- **scale**：图像的比例因子，其值如`1.0`、`2.0` 或 `3.0`。
- **orientation**：图像的方向。默认值为 [up](Orientation/up.zh-Hans.md)。
- **label**：与图像相关联的标签。SwiftUI 使用该标签进行访问。

## 创建用作控件的图像

- **init(_:bundle:label:)**：创建一个带标签的图像，您可以使用指定的标签将其作为控件的内容。
- **init(_:variableValue:bundle:label:)**：创建带标签的图像，可用作控件的内容，并带有指定的标签和变量值。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(_:scale:orientation:label:)
crawled: 2025-12-01T09:18:18Z
---

# init(_:scale:orientation:label:)

**Initializer**

Creates a labeled image based on a Core Graphics image instance, usable as content for controls.

## Declaration

```swift
init(_ cgImage: CGImage, scale: CGFloat, orientation: Image.Orientation = .up, label: Text)
```

## Parameters

- **cgImage**: The base graphical image.
- **scale**: The scale factor for the image, with a value like `1.0`, `2.0`, or `3.0`.
- **orientation**: The orientation of the image. The default is [up](Orientation/up.zh-Hans.md).
- **label**: The label associated with the image. SwiftUI uses the label for accessibility.

## Creating an image for use as a control

- **init(_:bundle:label:)**: Creates a labeled image that you can use as content for controls, with the specified label.
- **init(_:variableValue:bundle:label:)**: Creates a labeled image that you can use as content for controls, with the specified label and variable value.

