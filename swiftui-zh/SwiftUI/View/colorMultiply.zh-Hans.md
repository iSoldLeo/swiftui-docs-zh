--- 来源：https://developer.apple.com/documentation/SwiftUI/View/colorMultiply(_:)

抓取时间：2025-11-30T21:22:04Z

---

# colorMultiply(_:)

**实例方法**

为该视图添加颜色乘法效果。

## 声明

```swift
nonisolated func colorMultiply(_ color: Color) -> some View

```

## 参数

- **color**：要使该视图偏向的颜色。

## 返回值

带有颜色乘法效果的视图。

## 说明

以下示例并排显示了同一图像的两个版本；左侧是原始图像，右侧是应用了 `colorMultiply(_:)` 修饰符和 [purple](../ShapeStyle/purple.zh-Hans.md) 的副本。

```swift
struct InnerCircleView: View {
    var body: some View {
        Circle()
            .fill(Color.green)
            .frame(width: 40, height: 40, alignment: .center)
    }
}

struct ColorMultiply: View {
    var body: some View {
        HStack {
            Color.red.frame(width: 100, height: 100, alignment: .center)
                .overlay(InnerCircleView(), alignment: .center)
                .overlay(Text("Normal")
                             .font(.callout),
                         alignment: .bottom)
                .border(Color.gray)

            Spacer()

            Color.red.frame(width: 100, height: 100, alignment: .center)
                .overlay(InnerCircleView(), alignment: .center)
                .colorMultiply(Color.purple)
                .overlay(Text("Multiply")
                            .font(.callout),
                         alignment: .bottom)
                .border(Color.gray)
        }
        .padding(50)
    }
}
```

## 颜色变换

- **brightness(_:)**：按指定量提亮此视图。

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorInvert()**：反转此视图中的颜色。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色相旋转效果。

- **luminanceToAlpha()**：为此视图添加亮度到透明度（Alpha）效果。

- **materialActiveAppearance(_:)**：设置此视图中材质的显式激活外观。

- **materialActiveAppearance**：材质激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/colorMultiply(_:)
crawled: 2025-11-30T21:22:04Z
---

# colorMultiply(_:)

**Instance Method**

Adds a color multiplication effect to this view.

## Declaration

```swift
nonisolated func colorMultiply(_ color: Color) -> some View

```

## Parameters

- **color**: The color to bias this view toward.

## Return Value

A view with a color multiplication effect.

## Discussion

The following example shows two versions of the same image side by side; at left is the original, and at right is a duplicate with the `colorMultiply(_:)` modifier applied with [purple](../ShapeStyle/purple.zh-Hans.md).

```swift
struct InnerCircleView: View {
    var body: some View {
        Circle()
            .fill(Color.green)
            .frame(width: 40, height: 40, alignment: .center)
    }
}

struct ColorMultiply: View {
    var body: some View {
        HStack {
            Color.red.frame(width: 100, height: 100, alignment: .center)
                .overlay(InnerCircleView(), alignment: .center)
                .overlay(Text("Normal")
                             .font(.callout),
                         alignment: .bottom)
                .border(Color.gray)

            Spacer()

            Color.red.frame(width: 100, height: 100, alignment: .center)
                .overlay(InnerCircleView(), alignment: .center)
                .colorMultiply(Color.purple)
                .overlay(Text("Multiply")
                            .font(.callout),
                         alignment: .bottom)
                .border(Color.gray)
        }
        .padding(50)
    }
}
```



## Transforming colors

- **brightness(_:)**: Brightens this view by the specified amount.
- **contrast(_:)**: Sets the contrast and separation between similar colors in this view.
- **colorInvert()**: Inverts the colors in this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

