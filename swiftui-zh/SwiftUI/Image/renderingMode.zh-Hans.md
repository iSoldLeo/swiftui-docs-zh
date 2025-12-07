---
来源： https://developer.apple.com/documentation/SwiftUI/Image/renderingMode(_:)
抓取时间： 2025-12-01T09:18:27Z
---

# renderingMode(_:)

**实例方法**

指示 SwiftUI 是按原样渲染图像，还是使用不同的模式渲染图像。

## 声明

```swift
func renderingMode(_ renderingMode: Image.TemplateRenderingMode?) -> Image
```

## 参数

- **renderingMode**：SwiftUI 用来渲染图像的模式。

## 返回值

修改后的[Image](../Image.zh-Hans.md)。

## 讨论

[TemplateRenderingMode](TemplateRenderingMode.zh-Hans.md)枚举有两种情况：[original](TemplateRenderingMode/original.zh-Hans.md)和[template](TemplateRenderingMode/template.zh-Hans.md)。原始模式渲染原始源图像中出现的像素。模板模式会将所有不透明的像素渲染为前景色，你可以将其用于创建图像遮罩等用途。

下面的示例显示了这两种呈现模式在绿色圆圈和深绿色边框图标图像中的应用：

```swift
Image("dot_green")
    .renderingMode(.original)
Image("dot_green")
    .renderingMode(.template)
```



您还可以使用`renderingMode` 从 SF 符号集生成多色系统图形。使用[original](TemplateRenderingMode/original.zh-Hans.md) 模式可将前景色应用于符号的所有部分，但图形中具有独特颜色的部分除外。下面的示例显示了`person.crop.circle.badge.plus` 符号的三种用法，以实现不同的效果：

- 默认外观，未指定前景色或模板渲染模式。在亮色模式下，符号显示为全黑，而在暗色模式下则显示为全白。
- 通过使用`original` 模板渲染模式和蓝色前景色实现的多色行为。这种模式会使图形覆盖图像中特殊部分的前景色，在本例中就是加号图标。
- 通过使用`template` 渲染模式和蓝色前景色实现单色模板行为。无论用户的 "外观 "偏好如何，该模式都会将前景色应用于整个图像。

```swift
HStack {
   Image(systemName: "person.crop.circle.badge.plus")
   Image(systemName: "person.crop.circle.badge.plus")
       .renderingMode(.original)
       .foregroundColor(.blue)
   Image(systemName: "person.crop.circle.badge.plus")
       .renderingMode(.template)
       .foregroundColor(.blue)
}
.font(.largeTitle)
```



使用 SF Symbols 应用程序查找提供多色功能的系统图像。请记住，有些多色符号同时使用前景色和重点色。

## 指定呈现行为

- **antialiased(_:)**：指定 SwiftUI 在渲染图像时是否应用抗锯齿。
- **symbolRenderingMode(_:)**：设置此视图中符号图像的渲染模式。
- **interpolation(_:)**：指定渲染需要插值的图像时的当前质量级别。
- **Image.TemplateRenderingMode**：表示 SwiftUI 如何渲染图像的类型。
- **Image.Interpolation**：用于渲染需要插值的图像（如缩放图像）的质量级别。


---
source: https://developer.apple.com/documentation/SwiftUI/Image/renderingMode(_:)
crawled: 2025-12-01T09:18:27Z
---

# renderingMode(_:)

**Instance Method**

Indicates whether SwiftUI renders an image as-is, or by using a different mode.

## Declaration

```swift
func renderingMode(_ renderingMode: Image.TemplateRenderingMode?) -> Image
```

## Parameters

- **renderingMode**: The mode SwiftUI uses to render images.

## Return Value

A modified [Image](../Image.zh-Hans.md).

## Discussion

The [TemplateRenderingMode](TemplateRenderingMode.zh-Hans.md) enumeration has two cases: [original](TemplateRenderingMode/original.zh-Hans.md) and [template](TemplateRenderingMode/template.zh-Hans.md). The original mode renders pixels as they appear in the original source image. Template mode renders all nontransparent pixels as the foreground color, which you can use for purposes like creating image masks.

The following example shows both rendering modes, as applied to an icon image of a green circle with darker green border:

```swift
Image("dot_green")
    .renderingMode(.original)
Image("dot_green")
    .renderingMode(.template)
```



You also use `renderingMode` to produce multicolored system graphics from the SF Symbols set. Use the [original](TemplateRenderingMode/original.zh-Hans.md) mode to apply a foreground color to all parts of the symbol except those that have a distinct color in the graphic. The following example shows three uses of the `person.crop.circle.badge.plus` symbol to achieve different effects:

- A default appearance with no foreground color or template rendering mode specified. The symbol appears all black in light mode, and all white in Dark Mode.
- The multicolor behavior achieved by using `original` template rendering mode, along with a blue foreground color. This mode causes the graphic to override the foreground color for distinctive parts of the image, in this case the plus icon.
- A single-color template behavior achieved by using `template` rendering mode with a blue foreground color. This mode applies the foreground color to the entire image, regardless of the user’s Appearance preferences.

```swift
HStack {
   Image(systemName: "person.crop.circle.badge.plus")
   Image(systemName: "person.crop.circle.badge.plus")
       .renderingMode(.original)
       .foregroundColor(.blue)
   Image(systemName: "person.crop.circle.badge.plus")
       .renderingMode(.template)
       .foregroundColor(.blue)
}
.font(.largeTitle)
```



Use the SF Symbols app to find system images that offer the multicolor feature. Keep in mind that some multicolor symbols use both the foreground and accent colors.

## Specifying rendering behavior

- **antialiased(_:)**: Specifies whether SwiftUI applies antialiasing when rendering the image.
- **symbolRenderingMode(_:)**: Sets the rendering mode for symbol images within this view.
- **interpolation(_:)**: Specifies the current level of quality for rendering an image that requires interpolation.
- **Image.TemplateRenderingMode**: A type that indicates how SwiftUI renders images.
- **Image.Interpolation**: The level of quality for rendering an image that requires interpolation, such as a scaled image.

