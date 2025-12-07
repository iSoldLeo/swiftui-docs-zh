---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/shader(_:bounds:)
抓取时间： 2025-12-03T17:19:52Z
---

# shader(_:bounds:)

**类型方法**

返回一个着色器实例，该实例填充了每个像素的着色器查询结果。

## 声明

```swift
static func shader(_ shader: Shader, bounds: CGRect = .zero) -> GraphicsContext.Shading
```

## 参数

- **shader**：定义填充颜色的着色器。
- **bounds**：用于定义着色器的`bounds` 参数的矩形。

## 返回值

使用着色器填充的着色实例。

## 讨论

要让着色器函数充当形状填充，它必须有一个与之匹配的函数签名：

```swift
[[ stitchable ]] half4 name(float2 position, args...)
```

其中，`position` 是应用到着色器的像素的用户空间坐标，`args...` 应与绑定到 `shader` 的统一参数兼容。函数应返回目的地色彩空间（通常为 sRGB）中的预乘色彩值。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/Shading/shader(_:bounds:)
crawled: 2025-12-03T17:19:52Z
---

# shader(_:bounds:)

**Type Method**

Returns a shading instance that fills with the results of querying a shader for each pixel.

## Declaration

```swift
static func shader(_ shader: Shader, bounds: CGRect = .zero) -> GraphicsContext.Shading
```

## Parameters

- **shader**: The shader defining the filled colors.
- **bounds**: The rect used to define any `bounds` arguments of the shader.

## Return Value

A shading instance that fills using the shader.

## Discussion

For a shader function to act as a shape fill it must have a function signature matching:

```swift
[[ stitchable ]] half4 name(float2 position, args...)
```

where `position` is the user-space coordinates of the pixel applied to the shader, and `args...` should be compatible with the uniform arguments bound to `shader`. The function should return the premultiplied color value in the color space of the destination (typically sRGB).

