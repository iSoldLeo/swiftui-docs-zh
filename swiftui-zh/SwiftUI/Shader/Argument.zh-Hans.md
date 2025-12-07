--- 来源：https://developer.apple.com/documentation/SwiftUI/Shader/Argument

抓取时间：2025-12-03T06:33:58Z

---

# Shader.Argument

**Structure**

一个用于着色器函数的统一参数值。

## 声明

```swift
struct Argument
```

## 创建参数值

- **boundingRect**：返回一个参数值，表示着色器所附加的形状或视图的边界矩形，如 `float4(x, y, width, height)` 所示。对于没有自然边界矩形的着色器（例如，绘制到 `GraphicsContext` 中的滤镜效果），此值为未定义。

- **color(_:)**：返回一个表示 `color` 的参数值。当传递给 MSL 函数时，它将转换为 `half4` 值，即目标颜色空间中的预乘颜色值。

- **colorArray(_:)**：返回一个由提供的颜色值数组定义的参数值。当传递给 MSL 函数时，它将转换为 `device const half4 *ptr, int count` 一对参数。

- **data(_:)**：返回一个由提供的数据值定义的参数值。当传递给 MSL 函数时，它将转换为 `device const void *ptr, int size_in_bytes` 一对参数。

- **float(_:)**：返回一个表示 MSL 值 `float(x)` 的参数值。

- **float2(_:)**：返回一个表示 MSL 值 `float2(point.x, point.y)` 的参数值。

- **float2(_:_:)**：返回一个表示 MSL 值 `float2(x, y)` 的参数值。

- **float3(_:_:_:)**：返回一个表示 MSL 值 `float3(x, y, z)` 的参数值。

- **float4(_:_:_:_:)**：返回一个表示 MSL 值 `float4(x, y, z, w)` 的参数值。

- **floatArray(_:)**：返回一个由提供的浮点数数组定义的参数值。当传递给 MSL 函数时，它将转换为一对参数 `device const float *ptr, int count`。

- **image(_:)**：返回一个由提供的图像定义的参数值。当传递给 MSL 函数时，它将转换为 `texture2d<half>` 值。目前每个 `Shader` 实例仅支持一个图像参数。

## 创建着色器

- **init(function:arguments:)**：根据函数和要绑定到该函数的 uniform 参数值创建一个新的着色器。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Shader/Argument
crawled: 2025-12-03T06:33:58Z
---

# Shader.Argument

**Structure**

A single uniform argument value to a shader function.

## Declaration

```swift
struct Argument
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
- **image(_:)**: Returns an argument value defined by the provided image. When passed to an MSL function it will convert to a `texture2d<half>` value. Currently only one image parameter is supported per `Shader` instance.

## Creating a shader

- **init(function:arguments:)**: Creates a new shader from a function and the uniform argument values to bind to the function.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

