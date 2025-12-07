--- 来源：https://developer.apple.com/documentation/SwiftUI/View/saturation(_:)

抓取时间：2025-12-02T17:37:01Z

---

# saturation(_:)

**实例方法**

调整此视图的颜色饱和度。

## 声明

```swift
nonisolated func saturation(_ amount: Double) -> some View

```

## 参数

- **amount**：要应用于此视图的饱和度值。

## 返回值

一个调整了此视图饱和度的视图。

## 说明

使用颜色饱和度来增加或减少视图中颜色的强度。

以下示例展示了一系列红色方块，其饱和度从 0（灰色）到 100%（纯红色）以 20% 的增量递增：

```swift
struct Saturation: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Color.red.frame(width: 60, height: 60, alignment: .center)
                    .saturation(Double($0) * 0.2)
                    .overlay(Text("\(Double($0) * 0.2 * 100, specifier: "%.0f")%"),
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

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色相旋转效果。

- **luminanceToAlpha()**：为该视图添加亮度到透明度（Alpha）效果。

- **materialActiveAppearance(_:)**：为该视图中的材质设置显式激活外观。

- **materialActiveAppearance**：材质激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/saturation(_:)
crawled: 2025-12-02T17:37:01Z
---

# saturation(_:)

**Instance Method**

Adjusts the color saturation of this view.

## Declaration

```swift
nonisolated func saturation(_ amount: Double) -> some View

```

## Parameters

- **amount**: The amount of saturation to apply to this view.

## Return Value

A view that adjusts the saturation of this view.

## Discussion

Use color saturation to increase or decrease the intensity of colors in a view.

The example below shows a series of red squares with their saturation increasing from 0 (gray) to 100% (fully-red) in 20% increments:

```swift
struct Saturation: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Color.red.frame(width: 60, height: 60, alignment: .center)
                    .saturation(Double($0) * 0.2)
                    .overlay(Text("\(Double($0) * 0.2 * 100, specifier: "%.0f")%"),
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
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

