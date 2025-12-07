---
来源： https://developer.apple.com/documentation/SwiftUI/ShaderFunction
抓取时间： 2025-12-02T17:37:52Z
---

# 着色函数

**Structure**

对 Metal 着色器库中函数的引用。

## 声明

```swift
@dynamicCallable struct ShaderFunction
```

## 创建着色器函数

- **init(library:name:)**：根据提供的着色器库和函数名称字符串创建新的函数引用。

## 配置函数

- **library**：存储函数的着色器库。
- **name**：库中着色器函数的名称。
- **dynamicallyCall(withArguments:)**：通过将提供的参数值应用到引用的函数，返回一个新的着色器。

## 访问金属着色器

- **colorEffect(_:isEnabled:)**：返回一个新视图，将`shader` 应用到`self`，作为每个像素颜色的滤镜效果。
- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回将`shader` 应用到`self` 的新视图，作为每个像素位置的几何扭曲效果。
- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，在由`self` 创建的栅格图层上将`shader` 作为过滤器应用到`self`。
- **Shader**：对 Metal 着色器库中函数的引用，以及其绑定的统一参数值。
- **ShaderLibrary**：一个 Metal 着色器库。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/ShaderFunction
crawled: 2025-12-02T17:37:52Z
---

# ShaderFunction

**Structure**

A reference to a function in a Metal shader library.

## Declaration

```swift
@dynamicCallable struct ShaderFunction
```

## Creating a shader function

- **init(library:name:)**: Creates a new function reference from the provided shader library and function name string.

## Configuring a function

- **library**: The shader library storing the function.
- **name**: The name of the shader function in the library.
- **dynamicallyCall(withArguments:)**: Returns a new shader by applying the provided argument values to the referenced function.

## Accessing Metal shaders

- **colorEffect(_:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.
- **Shader**: A reference to a function in a Metal shader library, along with its bound uniform argument values.
- **ShaderLibrary**: A Metal shader library.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

