--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contrast(_:)

抓取时间：2025-12-02T17:36:59Z

---

# contrast(_:)

**实例方法**

设置此视图中相似颜色之间的对比度和分离度。

## 声明

```swift
nonisolated func contrast(_ amount: Double) -> some View

```

## 参数

- **amount**：要应用的颜色对比度强度。负值除了应用对比度外，还会反转颜色。

## 返回值

一个应用了颜色对比度的视图。

## 说明

对视图应用对比度，以增加或减少视图中相似颜色之间的分离度。

在下面的示例中，`contrast(_:)` 修饰符应用于一组红色正方形，每个正方形都包含一个对比鲜明的绿色内圆。在循环的每一步中，`contrast(_:)` 修饰符都会以 20% 的增量改变圆形/方形视图的对比度。对比度范围从 -20%（颜色反转——红色正方形变为浅绿色，绿色圆形变为淡紫色），到 0%（中性灰），再到 100%（亮红色正方形/亮绿色圆形）。应用负对比度值（如 -20% 正方形所示）会在反转颜色的同时增加对比度。

```swift
struct CircleView: View {
    var body: some View {
        Circle()
            .fill(Color.green)
            .frame(width: 25, height: 25, alignment: .center)
    }
}

struct Contrast: View {
    var body: some View {
        HStack {
            ForEach(-1..<6) {
                Color.red.frame(width: 50, height: 50, alignment: .center)
                    .overlay(CircleView(), alignment: .center)
                    .contrast(Double($0) * 0.2)
                    .overlay(Text("\(Double($0) * 0.2 * 100, specifier: "%.0f")%")
                                 .font(.callout),
                             alignment: .bottom)
                    .border(Color.gray)
            }
        }
    }
}
```

## 颜色变换

- **brightness(_:)**：将此视图亮度提高指定值。

- **colorInvert()**：反转此视图中的颜色。

- **colorMultiply(_:)**：为此视图添加颜色乘法效果。

- **saturation(_:)**：调整此视图的颜色饱和度。

- **grayscale(_:)**：为此视图添加灰度效果。

- **hueRotation(_:)**：为此视图应用色调旋转效果。

- **luminanceToAlpha()**：为此视图添加亮度到透明度 (Alpha) 的效果。

- **materialActiveAppearance(_:)**：为此视图中的材质设置显式激活外观。

- **materialActiveAppearance**：材质在其激活状态下应使用的行为，默认值为 `automatic`。

- **MaterialActiveAppearance**：材质激活和非激活状态下的外观行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contrast(_:)
crawled: 2025-12-02T17:36:59Z
---

# contrast(_:)

**Instance Method**

Sets the contrast and separation between similar colors in this view.

## Declaration

```swift
nonisolated func contrast(_ amount: Double) -> some View

```

## Parameters

- **amount**: The intensity of color contrast to apply. negative values invert colors in addition to applying contrast.

## Return Value

A view that applies color contrast to this view.

## Discussion

Apply contrast to a view to increase or decrease the separation between similar colors in the view.

In the example below, the `contrast(_:)` modifier is applied to a set of red squares each containing a contrasting green inner circle. At each step in the loop, the `contrast(_:)` modifier changes the contrast of the circle/square view in 20% increments. This ranges from -20% contrast (yielding inverted colors — turning the red square to pale-green and the green circle to mauve), to neutral-gray at 0%, to 100% contrast (bright-red square / bright-green circle). Applying negative contrast values, as shown in the -20% square, will apply contrast in addition to inverting colors.

```swift
struct CircleView: View {
    var body: some View {
        Circle()
            .fill(Color.green)
            .frame(width: 25, height: 25, alignment: .center)
    }
}

struct Contrast: View {
    var body: some View {
        HStack {
            ForEach(-1..<6) {
                Color.red.frame(width: 50, height: 50, alignment: .center)
                    .overlay(CircleView(), alignment: .center)
                    .contrast(Double($0) * 0.2)
                    .overlay(Text("\(Double($0) * 0.2 * 100, specifier: "%.0f")%")
                                 .font(.callout),
                             alignment: .bottom)
                    .border(Color.gray)
            }
        }
    }
}
```



## Transforming colors

- **brightness(_:)**: Brightens this view by the specified amount.
- **colorInvert()**: Inverts the colors in this view.
- **colorMultiply(_:)**: Adds a color multiplication effect to this view.
- **saturation(_:)**: Adjusts the color saturation of this view.
- **grayscale(_:)**: Adds a grayscale effect to this view.
- **hueRotation(_:)**: Applies a hue rotation effect to this view.
- **luminanceToAlpha()**: Adds a luminance to alpha effect to this view.
- **materialActiveAppearance(_:)**: Sets an explicit active appearance for materials in this view.
- **materialActiveAppearance**: The behavior materials should use for their active state, defaulting to `automatic`.
- **MaterialActiveAppearance**: The behavior for how materials appear active and inactive.

