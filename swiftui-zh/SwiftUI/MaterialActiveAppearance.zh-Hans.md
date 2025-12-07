--- 来源：https://developer.apple.com/documentation/SwiftUI/MaterialActiveAppearance
抓取时间：2025-12-02T17:37:04Z

---

# MaterialActiveAppearance

**Structure**

材质激活和非激活状态的显示方式。

## 声明

```swift
struct MaterialActiveAppearance
```

## 概述

在 macOS 系统中，材质具有激活和非激活两种状态，可以增强其所在窗口的激活状态：

- 用作 `window` 容器背景的材质和 `bar` 材质在其所在的窗口处于非激活状态时，将显示为非激活状态。

- 所有其他材质默认始终显示为激活状态。

可以显式设置激活状态以覆盖材质的默认行为。例如，可以将用作 `window` 容器背景的材质设置为始终处于活动状态：

```swift
Text("Hello, World!")
    .containerBackground(
        Material.regular.materialActiveAppearance(.active),
        for: .window)
```

## 类型属性

- **active**：材质将始终处于活动状态。

- **automatic**：材质将根据上下文和平台约定自动显示为活动或非活动状态。

- **inactive**：材质将始终显示为非活动状态。

- **matchWindow**：材质的显示状态将取决于其窗口的活动状态。

## 颜色变换

- **brightness(_:)**：按指定量调亮此视图。

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转此视图中的颜色。

- **colorMultiply(_:)**：为此视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色相旋转效果。

- **luminanceToAlpha()**：为此视图添加亮度到透明度效果。

- **materialActiveAppearance(_:)**：为此视图中的材质设置显式激活外观。

- **materialActiveAppearance**：材质在其激活状态下应使用的行为，默认值为 `automatic`。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/MaterialActiveAppearance
crawled: 2025-12-02T17:37:04Z
---

# MaterialActiveAppearance

**Structure**

The behavior for how materials appear active and inactive.

## Declaration

```swift
struct MaterialActiveAppearance
```

## Overview

On macOS, materials have active and inactive appearances that can reinforce the active appearance of the window they are in:

- Materials used as a `window` container background and `bar` materials will appear inactive when their containing window is inactive.
- All other materials will always appear active by default.

An explicit active appearance can be set to override a material’s default behavior. For example, materials used as the `window` container background can be made to always appear active by setting the active appearance behavior to be always active:

```swift
Text("Hello, World!")
    .containerBackground(
        Material.regular.materialActiveAppearance(.active),
        for: .window)
```

## Type Properties

- **active**: Materials will always appear active.
- **automatic**: Materials will automatically appear active or inactive based on context and platform convention.
- **inactive**: Materials will always appear inactive.
- **matchWindow**: Materials will have an active or inactive appearance based on the active appearance of their window.

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
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

