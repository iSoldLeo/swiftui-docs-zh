--- 来源：https://developer.apple.com/documentation/SwiftUI/View/materialActiveAppearance(_:)

抓取时间：2025-12-02T17:24:48Z

---

# materialActiveAppearance(_:)

**实例方法**

为该视图中的材质设置显式激活外观。

## 声明

```swift
nonisolated func materialActiveAppearance(_ appearance: MaterialActiveAppearance) -> some View

```

## 颜色变换

- **brightness(_:)**：按指定幅度提亮该视图。

- **contrast(_:)**：设置该视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转该视图中的颜色。

- **colorMultiply(_:)**：为该视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色调旋转效果。

- **luminanceToAlpha()**：为此视图添加亮度到透明度（Alpha）效果。

- **materialActiveAppearance**：材质在其激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/materialActiveAppearance(_:)
crawled: 2025-12-02T17:24:48Z
---

# materialActiveAppearance(_:)

**Instance Method**

Sets an explicit active appearance for materials in this view.

## Declaration

```swift
nonisolated func materialActiveAppearance(_ appearance: MaterialActiveAppearance) -> some View

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
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

