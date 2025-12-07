---

来源：https://developer.apple.com/documentation/SwiftUI/View/colorInvert()

抓取时间：2025-12-02T17:36:59Z

---

# colorInvert()

**实例方法**

反转此视图中的颜色。

## 声明

```swift
nonisolated func colorInvert() -> some View

```

## 返回值

一个颜色反转后的视图。

## 说明

`colorInvert()` 修饰符会反转视图中的所有颜色，使每种颜色显示为其互补色。例如，蓝色变为黄色，白色变为黑色。

在下面的示例中，两个红色正方形各自包含一个绿色圆圈。反转后的正方形显示了正方形颜色的效果：红色和绿色的互补色——青色和紫色。

```swift
struct InnerCircleView: View {
    var body: some View {
        Circle()
            .fill(Color.green)
            .frame(width: 40, height: 40, alignment: .center)
    }
}

struct ColorInvert: View {
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
                .colorInvert()
                .overlay(Text("Inverted")
                             .font(.callout),
                         alignment: .bottom)
                .border(Color.gray)
        }
        .padding(50)
    }
}
```

## 颜色变换

- **brightness(_:)**：按指定量提高此视图的亮度。

- **contrast(_:)**：设置此视图中相似颜色之间的对比度和分离度。

- **colorMultiply(_:)**：为此视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色相旋转效果。

- **luminanceToAlpha()**：为此视图添加亮度到透明度 (Alpha) 的效果。

- **materialActiveAppearance(_:)**：设置此视图中材质的显式激活外观。

- **materialActiveAppearance**：材质激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/colorInvert()
crawled: 2025-12-02T17:36:59Z
---

# colorInvert()

**Instance Method**

Inverts the colors in this view.

## Declaration

```swift
nonisolated func colorInvert() -> some View

```

## Return Value

A view that inverts its colors.

## Discussion

The `colorInvert()` modifier inverts all of the colors in a view so that each color displays as its complementary color. For example, blue converts to yellow, and white converts to black.

In the example below, two red squares each have an interior green circle. The inverted square shows the effect of the square’s colors: complimentary colors for red and green — teal and purple.

```swift
struct InnerCircleView: View {
    var body: some View {
        Circle()
            .fill(Color.green)
            .frame(width: 40, height: 40, alignment: .center)
    }
}

struct ColorInvert: View {
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
                .colorInvert()
                .overlay(Text("Inverted")
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
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

