--- 来源：https://developer.apple.com/documentation/SwiftUI/View/brightness(_:)

抓取时间：2025-11-30T21:22:02Z

---

# brightness(_:)

**实例方法**

将当前视图亮度提高指定的数值。

## 声明

```swift
nonisolated func brightness(_ amount: Double) -> some View

```

## 参数

- **amount**：介于 0（无效果）和 1（完全调白）之间的值，表示亮度效果的强度。

## 返回值

将当前视图亮度提高指定的数值后，返回一个新视图。

## 说明

使用 `brightness(_:)` 可以提高视图中颜色的亮度。以下示例显示了一系列红色方块，其亮度从 0（纯红）到 100%（纯白），以 20% 为增量递增。

```swift
struct Brightness: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Color.red.frame(width: 60, height: 60, alignment: .center)
                    .brightness(Double($0) * 0.2)
                    .overlay(Text("\(Double($0) * 0.2 * 100, specifier: "%.0f")%"),
                             alignment: .bottom)
                    .border(Color.gray)
            }
        }
    }
}
```

## 颜色变换

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转此视图中的颜色。

- **colorMultiply(_:)**：为此视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色相旋转效果。

- **luminanceToAlpha()**：为该视图添加亮度到透明度（Alpha）效果。

- **materialActiveAppearance(_:)**：为该视图中的材质设置显式激活外观。

- **materialActiveAppearance**：材质激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/brightness(_:)
crawled: 2025-11-30T21:22:02Z
---

# brightness(_:)

**Instance Method**

Brightens this view by the specified amount.

## Declaration

```swift
nonisolated func brightness(_ amount: Double) -> some View

```

## Parameters

- **amount**: A value between 0 (no effect) and 1 (full white brightening) that represents the intensity of the brightness effect.

## Return Value

A view that brightens this view by the specified amount.

## Discussion

Use `brightness(_:)` to brighten the intensity of the colors in a view. The example below shows a series of red squares, with their brightness increasing from 0 (fully red) to 100% (white) in 20% increments.

```swift
struct Brightness: View {
    var body: some View {
        HStack {
            ForEach(0..<6) {
                Color.red.frame(width: 60, height: 60, alignment: .center)
                    .brightness(Double($0) * 0.2)
                    .overlay(Text("\(Double($0) * 0.2 * 100, specifier: "%.0f")%"),
                             alignment: .bottom)
                    .border(Color.gray)
            }
        }
    }
}
```



## Transforming colors

- **contrast(_:)**: Sets the contrast and separation between similar colors in this view.
- **colorInvert()**: Inverts the colors in this view.
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

