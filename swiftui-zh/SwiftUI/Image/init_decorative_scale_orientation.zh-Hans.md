---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(装饰:比例:方向:)
抓取时间：2025-12-01T09:18:20Z
---

# init(decorative:scale:orientation:)

**Initializer**

根据 Core Graphics 图像实例创建无标记的装饰图像。

### 声明

```swift
init(decorative cgImage: CGImage, scale: CGFloat, orientation: Image.Orientation = .up)
```

## 参数

- **cgImage**：基础图形图像。
- **scale**：图像的比例因子，其值如`1.0`、`2.0` 或 `3.0`。
- **orientation**：图像的方向。默认值为 [up](Orientation/up.zh-Hans.md)。

## 讨论

为了便于访问，SwiftUI 会忽略此图像。

## 创建装饰用图像

- **init(decorative:bundle:)**：创建一个无标记的装饰性图像。
- **init(decorative:variableValue:bundle:)**：创建一个无标记的装饰图像，图像值可变。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(decorative:scale:orientation:)
crawled: 2025-12-01T09:18:20Z
---

# init(decorative:scale:orientation:)

**Initializer**

Creates an unlabeled, decorative image based on a Core Graphics image instance.

## Declaration

```swift
init(decorative cgImage: CGImage, scale: CGFloat, orientation: Image.Orientation = .up)
```

## Parameters

- **cgImage**: The base graphical image.
- **scale**: The scale factor for the image, with a value like `1.0`, `2.0`, or `3.0`.
- **orientation**: The orientation of the image. The default is [up](Orientation/up.zh-Hans.md).

## Discussion

SwiftUI ignores this image for accessibility purposes.

## Creating an image for decorative use

- **init(decorative:bundle:)**: Creates an unlabeled, decorative image.
- **init(decorative:variableValue:bundle:)**: Creates an unlabeled, decorative image, with a variable value.

