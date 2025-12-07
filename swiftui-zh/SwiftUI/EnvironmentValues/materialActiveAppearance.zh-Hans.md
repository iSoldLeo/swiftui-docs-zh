---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/materialActiveAppearance
抓取时间： 2025-12-02T17:37:04Z
---

# MaterialActiveAppearance

**实例属性**

材料在活动状态下应使用的行为，默认为 `automatic`。

## 声明

```swift
var materialActiveAppearance: MaterialActiveAppearance { get set }
```

## 转换颜色

- **brightness(_:)**：按指定的量增亮该视图。
- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分隔度。
- **colorInvert()**：反转此视图中的颜色。
- **colorMultiply(_:)**：为该视图添加颜色倍增效果。
- **saturation(_:)**：调整此视图的色彩饱和度。
- **grayscale(_:)**：为该视图添加灰度效果。
- **hueRotation(_:)**：为该视图应用色调旋转效果。
- **luminanceToAlpha()**：为该视图添加亮度到 Alpha 的效果。
- **materialActiveAppearance(_:)**：为该视图中的材质设置显式活动外观。
- **MaterialActiveAppearance**：物料如何显示活动和非活动的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/materialActiveAppearance
crawled: 2025-12-02T17:37:04Z
---

# materialActiveAppearance

**Instance Property**

The behavior materials should use for their active state, defaulting to `automatic`.

## Declaration

```swift
var materialActiveAppearance: MaterialActiveAppearance { get set }
```

## Transforming colors

- **brightness(_:)**: Brightens this view by the specified amount.
- **contrast(_:)**: Sets the contrast and separation between similar colors in this view.
- **colorInvert()**: Inverts the colors in this view.
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

