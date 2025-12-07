--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hueRotation(_:)

抓取时间：2025-11-30T21:22:06Z

---

# hueRotation(_:)

**实例方法**

为该视图应用色调旋转效果。

## 声明

```swift
nonisolated func hueRotation(_ angle: Angle) -> some View

```

## 参数

- **angle**：要应用于该视图中颜色的色调旋转角度。

## 返回值

一个应用了色调旋转效果的视图。

## 说明

使用色调旋转效果可以根据您指定的角度移动视图中的所有颜色。

以下示例显示了一系列填充了线性渐变的正方形。每个方格显示了 36° 色调旋转（5 个方格共旋转 180°）对渐变的影响：

```swift
struct HueRotation: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Rectangle()
                    .fill(.linearGradient(
                        colors: [.blue, .red, .green],
                        startPoint: .top, endPoint: .bottom))
                    .hueRotation((.degrees(Double($0 * 36))))
                    .frame(width: 60, height: 60, alignment: .center)
            }
        }
    }
}
```

## 颜色变换

- **brightness(_:)**：按指定量提亮此视图。

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转此视图中的颜色。

- **colorMultiply(_:)**：为此视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **luminanceToAlpha()**：为该视图添加亮度到透明度（Alpha）效果。

- **materialActiveAppearance(_:)**：为该视图中的材质设置显式激活外观。

- **materialActiveAppearance**：材质激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hueRotation(_:)
crawled: 2025-11-30T21:22:06Z
---

# hueRotation(_:)

**Instance Method**

Applies a hue rotation effect to this view.

## Declaration

```swift
nonisolated func hueRotation(_ angle: Angle) -> some View

```

## Parameters

- **angle**: The hue rotation angle to apply to the colors in this view.

## Return Value

A view that applies a hue rotation effect to this view.

## Discussion

Use hue rotation effect to shift all of the colors in a view according to the angle you specify.

The example below shows a series of squares filled with a linear gradient. Each square shows the effect of a 36˚ hueRotation (a total of 180˚ across the 5 squares) on the gradient:

```swift
struct HueRotation: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Rectangle()
                    .fill(.linearGradient(
                        colors: [.blue, .red, .green],
                        startPoint: .top, endPoint: .bottom))
                    .hueRotation((.degrees(Double($0 * 36))))
                    .frame(width: 60, height: 60, alignment: .center)
            }
        }
    }
}
```



## Transforming colors

- **brightness(_:)**: Brightens this view by the specified amount.
- **contrast(_:)**: Sets the contrast and separation between similar colors in this view.
- **colorInvert()**: Inverts the colors in this view.
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

