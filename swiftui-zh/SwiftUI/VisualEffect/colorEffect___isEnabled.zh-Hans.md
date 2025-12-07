---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/colorEffect(_:isEnabled:)
抓取时间： 2025-12-03T06:29:45Z
---

# colorEffect(_:isEnabled:)

**实例方法**

返回一个新的视觉效果，将`shader`应用到`self`，作为每个像素颜色的滤镜效果。

## 声明

```swift
func colorEffect(_ shader: Shader, isEnabled: Bool = true) -> some VisualEffect

```

## 参数

- **shader**：作为滤色器应用于`self` 的着色器。
- **isEnabled**：是否启用效果。

## 返回值

一个新视图，该视图将`self`着色器作为滤色器应用。

## 讨论

要将着色器函数用作滤色器，它必须有一个与之匹配的函数签名：

```swift
[[ stitchable ]] half4 name(float2 position, half4 color, args...)
```

其中，`position` 是应用到着色器的像素的用户空间坐标，`color` 是源颜色，作为目标颜色空间中的预乘颜色。`args...`应与绑定到`shader`的统一参数兼容。函数应返回修改后的颜色值。



## 调整颜色

- **brightness(_:)**：按指定量增亮视图。
- **contrast(_:)**：设置视图中相似颜色之间的对比度和分隔度。
- **grayscale(_:)**：为视图添加灰度效果。
- **hueRotation(_:)**：为视图应用色调旋转效果。
- **saturation(_:)**：调整视图的色彩饱和度。
- **opacity(_:)**：设置视图的透明度。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/colorEffect(_:isEnabled:)
crawled: 2025-12-03T06:29:45Z
---

# colorEffect(_:isEnabled:)

**Instance Method**

Returns a new visual effect that applies `shader` to `self` as a filter effect on the color of each pixel.

## Declaration

```swift
func colorEffect(_ shader: Shader, isEnabled: Bool = true) -> some VisualEffect

```

## Parameters

- **shader**: The shader to apply to `self` as a color filter.
- **isEnabled**: Whether the effect is enabled or not.

## Return Value

A new view that renders `self` with the shader applied as a color filter.

## Discussion

For a shader function to act as a color filter it must have a function signature matching:

```swift
[[ stitchable ]] half4 name(float2 position, half4 color, args...)
```

where `position` is the user-space coordinates of the pixel applied to the shader and `color` its source color, as a pre-multiplied color in the destination color space. `args...` should be compatible with the uniform arguments bound to `shader`. The function should return the modified color value.



## Adjusting Color

- **brightness(_:)**: Brightens the view by the specified amount.
- **contrast(_:)**: Sets the contrast and separation between similar colors in the view.
- **grayscale(_:)**: Adds a grayscale effect to the view.
- **hueRotation(_:)**: Applies a hue rotation effect to the view.
- **saturation(_:)**: Adjusts the color saturation of the view.
- **opacity(_:)**: Sets the transparency of the view.

