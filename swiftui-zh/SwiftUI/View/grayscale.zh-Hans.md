--- 来源：https://developer.apple.com/documentation/SwiftUI/View/grayscale(_:)

抓取时间：2025-12-02T17:37:01Z

---

# grayscale(_:)

**实例方法**

为该视图添加灰度效果。

## 声明

```swift
nonisolated func grayscale(_ amount: Double) -> some View

```

## 参数

- **amount**：灰度强度，取值范围为 0.0 到小于 1.0。值越接近 0.0，色彩越鲜艳；值越接近 1.0，色彩越暗淡。

## 返回值

一个添加了灰度效果的视图。

## 说明

灰度效果会降低该视图中颜色的强度。

以下示例展示了一系列红色方块，它们的灰度效果从 0（最红）到 99%（完全去饱和），以大约 20% 的增量递增：

```swift
struct Saturation: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Color.red.frame(width: 60, height: 60, alignment: .center)
                    .grayscale(Double($0) * 0.1999)
                    .overlay(Text("\(Double($0) * 0.1999 * 100, specifier: "%.4f")%"),
                             alignment: .bottom)
                    .border(Color.gray)
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

- **hueRotation(_:)**：为此视图应用色相旋转效果。

- **luminanceToAlpha()**：为该视图添加亮度到透明度（Alpha）效果。

- **materialActiveAppearance(_:)**：为该视图中的材质设置显式激活外观。

- **materialActiveAppearance**：材质激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/grayscale(_:)
crawled: 2025-12-02T17:37:01Z
---

# grayscale(_:)

**Instance Method**

Adds a grayscale effect to this view.

## Declaration

```swift
nonisolated func grayscale(_ amount: Double) -> some View

```

## Parameters

- **amount**: The intensity of grayscale to apply from 0.0 to less than 1.0. Values closer to 0.0 are more colorful, and values closer to 1.0 are less colorful.

## Return Value

A view that adds a grayscale effect to this view.

## Discussion

A grayscale effect reduces the intensity of colors in this view.

The example below shows a series of red squares with their grayscale effect increasing from 0 (reddest) to 99% (fully desaturated) in approximate 20% increments:

```swift
struct Saturation: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Color.red.frame(width: 60, height: 60, alignment: .center)
                    .grayscale(Double($0) * 0.1999)
                    .overlay(Text("\(Double($0) * 0.1999 * 100, specifier: "%.4f")%"),
                             alignment: .bottom)
                    .border(Color.gray)
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
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

