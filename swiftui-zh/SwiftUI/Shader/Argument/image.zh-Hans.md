--- 来源：https://developer.apple.com/documentation/SwiftUI/Shader/Argument/image(_:)

抓取时间：2025-12-04T13:29:26Z

---

# image(_:)

**类型方法**

返回由提供的图像定义的参数值。当传递给 MSL 函数时，它将转换为 `texture2d<half>` 值。目前每个 `Shader` 实例仅支持一个图像参数。

## 声明

```swift
static func image(_ image: Image) -> Shader.Argument
```

## 创建参数值

- **boundingRect**：返回一个参数值，表示着色器所附加的形状或视图的边界矩形，类型为 `float4(x, y, width, height)`。对于没有自然边界矩形的着色器（例如，绘制到 `GraphicsContext` 中的滤镜效果），此值未定义。

- **color(_:)**：返回一个表示 `color` 的参数值。当传递给 MSL 函数时，它将转换为 `half4` 值，即目标颜色空间中的预乘颜色。

- **colorArray(_:)**：返回一个由提供的颜色值数组定义的参数值。当传递给 MSL 函数时，它将转换为一对 `device const half4 *ptr, int count` 参数。

- **data(_:)**：返回一个由提供的数据值定义的参数值。当传递给 MSL 函数时，它将转换为一对 `device const void *ptr, int size_in_bytes` 参数。

- **float(_:)**：返回一个表示 MSL 值 `float(x)` 的参数值。

- **float2(_:)**：返回一个表示 MSL 值 `float2(point.x, point.y)` 的参数值。

- **float2(_:_:)**：返回一个表示 MSL 值 `float2(x, y)` 的参数值。

- **float3(_:_:_:)**：返回一个表示 MSL 值 `float3(x, y, z)` 的参数值。

- **float4(_:_:_:_:)**：返回一个表示 MSL 值 `float4(x, y, z, w)` 的参数值。

- **floatArray(_:)**：返回一个由提供的浮点数数组定义的参数值。当传递给 MSL 函数时，它将转换为 `device const float *ptr, int count` 参数对。


---
source: https://developer.apple.com/documentation/SwiftUI/Shader/Argument/image(_:)
crawled: 2025-12-04T13:29:26Z
---

# image(_:)

**Type Method**

Returns an argument value defined by the provided image. When passed to an MSL function it will convert to a `texture2d<half>` value. Currently only one image parameter is supported per `Shader` instance.

## Declaration

```swift
static func image(_ image: Image) -> Shader.Argument
```

## Creating argument values

- **boundingRect**: Returns an argument value representing the bounding rect of the shape or view that the shader is attached to, as `float4(x, y, width, height)`. This value is undefined for shaders that do not have a natural bounding rect (e.g. filter effects drawn into `GraphicsContext`).
- **color(_:)**: Returns an argument value representing `color`. When passed to a MSL function it will convert to a `half4` value, as a premultiplied color in the target color space.
- **colorArray(_:)**: Returns an argument value defined by the provided array of color values. When passed to an MSL function it will convert to a `device const half4 *ptr, int count` pair of parameters.
- **data(_:)**: Returns an argument value defined by the provided data value. When passed to an MSL function it will convert to a `device const void *ptr, int size_in_bytes` pair of parameters.
- **float(_:)**: Returns an argument value representing the MSL value `float(x)`.
- **float2(_:)**: Returns an argument value representing the MSL value `float2(point.x, point.y)`.
- **float2(_:_:)**: Returns an argument value representing the MSL value `float2(x, y)`.
- **float3(_:_:_:)**: Returns an argument value representing the MSL value `float3(x, y, z)`.
- **float4(_:_:_:_:)**: Returns an argument value representing the MSL value `float4(x, y, z, w)`.
- **floatArray(_:)**: Returns an argument value defined by the provided array of floating point numbers. When passed to an MSL function it will convert to a `device const float *ptr, int count` pair of parameters.

