--- 来源：https://developer.apple.com/documentation/SwiftUI/View/shadow(color:radius:x:y:)

抓取时间：2025-11-30T21:22:30Z

---

# shadow(color:radius:x:y:)

**实例方法**

为该视图添加阴影。

## 声明

```swift
nonisolated func shadow(color: Color = Color(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0) -> some View

```

## 参数

- **color**：阴影的颜色。

- **radius**：阴影的模糊程度。值越大，模糊程度越高。

- **x**：阴影相对于视图的水平偏移量。

- **y**：阴影相对于视图的垂直偏移量。

## 返回值

一个为当前视图添加阴影的视图。

## 说明

使用此修改器可在视图后方添加指定颜色的阴影。您可以使用 `x` 和 `y` 参数分别在水平和垂直方向上偏移阴影。您还可以使用 `radius` 参数模糊阴影边缘。半径为零可创建锐利的阴影。半径值越大，阴影越柔和。

以下示例创建了一个具有不同偏移量和模糊度的方框网格。每个方框都显示了其半径和偏移量值以供参考。

```swift
struct Shadow: View {
    let steps = [0, 5, 10]

    var body: some View {
        VStack(spacing: 50) {
            ForEach(steps, id: \.self) { offset in
                HStack(spacing: 50) {
                    ForEach(steps, id: \.self) { radius in
                        Color.blue
                            .shadow(
                                color: .primary,
                                radius: CGFloat(radius),
                                x: CGFloat(offset), y: CGFloat(offset))
                            .overlay {
                                VStack {
                                    Text("\(radius)")
                                    Text("(\(offset), \(offset))")
                                }
                            }
                    }
                }
            }
        }
    }
}
```

上面的示例使用 [primary](../Color/primary.zh-Hans.md) 作为颜色，以便清晰地显示阴影。在实际应用中，您可能更喜欢柔和的颜色，例如 [gray](../Color/gray.zh-Hans.md)。如果未指定颜色，则该方法使用半透明黑色。

## 应用模糊和阴影

- **blur(radius:opaque:)**：对此视图应用高斯模糊。

- **ColorMatrix**：用于 RGBA 颜色变换的矩阵。


---
source: https://developer.apple.com/documentation/SwiftUI/View/shadow(color:radius:x:y:)
crawled: 2025-11-30T21:22:30Z
---

# shadow(color:radius:x:y:)

**Instance Method**

Adds a shadow to this view.

## Declaration

```swift
nonisolated func shadow(color: Color = Color(.sRGBLinear, white: 0, opacity: 0.33), radius: CGFloat, x: CGFloat = 0, y: CGFloat = 0) -> some View

```

## Parameters

- **color**: The shadow’s color.
- **radius**: A measure of how much to blur the shadow. Larger values result in more blur.
- **x**: An amount to offset the shadow horizontally from the view.
- **y**: An amount to offset the shadow vertically from the view.

## Return Value

A view that adds a shadow to this view.

## Discussion

Use this modifier to add a shadow of a specified color behind a view. You can offset the shadow from its view independently in the horizontal and vertical dimensions using the `x` and `y` parameters. You can also blur the edges of the shadow using the `radius` parameter. Use a radius of zero to create a sharp shadow. Larger radius values produce softer shadows.

The example below creates a grid of boxes with varying offsets and blur. Each box displays its radius and offset values for reference.

```swift
struct Shadow: View {
    let steps = [0, 5, 10]

    var body: some View {
        VStack(spacing: 50) {
            ForEach(steps, id: \.self) { offset in
                HStack(spacing: 50) {
                    ForEach(steps, id: \.self) { radius in
                        Color.blue
                            .shadow(
                                color: .primary,
                                radius: CGFloat(radius),
                                x: CGFloat(offset), y: CGFloat(offset))
                            .overlay {
                                VStack {
                                    Text("\(radius)")
                                    Text("(\(offset), \(offset))")
                                }
                            }
                    }
                }
            }
        }
    }
}
```



The example above uses [primary](../Color/primary.zh-Hans.md) as the color to make the shadow easy to see for the purpose of illustration. In practice, you might prefer something more subtle, like [gray](../Color/gray.zh-Hans.md). If you don’t specify a color, the method uses a semi-transparent black.

## Applying blur and shadows

- **blur(radius:opaque:)**: Applies a Gaussian blur to this view.
- **ColorMatrix**: A matrix to use in an RGBA color transformation.

