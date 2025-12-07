---
来源：https://developer.apple.com/documentation/SwiftUI/Image/init(size:label:opaque:colorMode:renderer:)
抓取时间：2025-12-03T04:29:01Z
---

# init(size:label:opaque:colorMode:renderer:)

**Initializer**

初始化指定大小的图像，图像内容由自定义渲染闭包提供。

## 声明

```swift
init(size: CGSize, label: Text? = nil, opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear, renderer: @escaping (inout GraphicsContext) -> Void)
```

## 参数

- **size**：新创建图像的大小。
- **label**：与图像关联的标签。SwiftUI 使用该标签进行访问。
- **opaque**：布尔值，表示图像是否完全不透明。这可能会在`true`.SY_0012⟧.时提高性能。不要向声明为不透明的图像渲染非不透明像素。默认为 `false`。
- **colorMode**：图像的工作色彩空间和存储格式。默认为 [nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md)。
- **renderer**：用于绘制图像内容的闭包。该闭包接收[GraphicsContext](../GraphicsContext.zh-Hans.md) 作为参数。

## 讨论

使用此初始化器，可以通过调用提供给`renderer` 闭包的[GraphicsContext](../GraphicsContext.zh-Hans.md) 上的绘图命令来创建图像。

下面的示例展示了通过传递`GraphicContext`来绘制椭圆并填充渐变色的自定义图像：

```swift
let mySize = CGSize(width: 300, height: 200)
let image = Image(size: mySize) { context in
    context.fill(
        Path(
            ellipseIn: CGRect(origin: .zero, size: mySize)),
            with: .linearGradient(
                Gradient(colors: [.yellow, .orange]),
                startPoint: .zero,
                endPoint: CGPoint(x: mySize.width, y:mySize.height))
    )
}
```




---
source: https://developer.apple.com/documentation/SwiftUI/Image/init(size:label:opaque:colorMode:renderer:)
crawled: 2025-12-03T04:29:01Z
---

# init(size:label:opaque:colorMode:renderer:)

**Initializer**

Initializes an image of the given size, with contents provided by a custom rendering closure.

## Declaration

```swift
init(size: CGSize, label: Text? = nil, opaque: Bool = false, colorMode: ColorRenderingMode = .nonLinear, renderer: @escaping (inout GraphicsContext) -> Void)
```

## Parameters

- **size**: The size of the newly-created image.
- **label**: The label associated with the image. SwiftUI uses the label for accessibility.
- **opaque**: A Boolean value that indicates whether the image is fully opaque. This may improve performance when `true`. Don’t render non-opaque pixels to an image declared as opaque. Defaults to `false`.
- **colorMode**: The working color space and storage format of the image. Defaults to [nonLinear](../ColorRenderingMode/nonLinear.zh-Hans.md).
- **renderer**: A closure to draw the contents of the image. The closure receives a [GraphicsContext](../GraphicsContext.zh-Hans.md) as its parameter.

## Discussion

Use this initializer to create an image by calling drawing commands on a [GraphicsContext](../GraphicsContext.zh-Hans.md) provided to the `renderer` closure.

The following example shows a custom image created by passing a `GraphicContext` to draw an ellipse and fill it with a gradient:

```swift
let mySize = CGSize(width: 300, height: 200)
let image = Image(size: mySize) { context in
    context.fill(
        Path(
            ellipseIn: CGRect(origin: .zero, size: mySize)),
            with: .linearGradient(
                Gradient(colors: [.yellow, .orange]),
                startPoint: .zero,
                endPoint: CGPoint(x: mySize.width, y:mySize.height))
    )
}
```



