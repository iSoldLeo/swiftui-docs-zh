--- 来源：https://developer.apple.com/documentation/SwiftUI/ShaderLibrary
抓取时间：2025-12-02T17:37:52Z

---

# ShaderLibrary

**Structure**

一个 Metal 着色器库。

## 声明

```swift
@dynamicMemberLookup struct ShaderLibrary
```

## 获取默认着色器库

- **default**：主（即 app）包的默认着色器库。

- **bundle(_:)**：返回指定包的默认着色器库。

## 创建着色器库

- **init(url:)**：根据 `url` 的内容创建一个新的 Metal 着色器库，`url` 必须是预编译 Metal 库的位置。从返回的库编译的函数仅在返回的库存在期间才会被缓存。

- **init(data:)**：从 `data` 创建一个新的 Metal 着色器库，`data` 必须是预编译的 Metal 库的内容。从返回的库编译的函数仅在返回的库存在期间才会被缓存。

## 访问着色器函数

- **subscript(dynamicMember:)**：返回一个新的着色器函数，该函数表示默认着色器库中名为 `name` 的可拼接 MSL 函数。

## 下标

- **subscript(dynamicMember:)**：返回一个新的着色器函数，该函数表示库中名为 `name` 的可拼接 MSL 函数。

## 访问 Metal 着色器

- **colorEffect(_:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的颜色，作为滤镜效果。

- **distortionEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于每个像素的位置，作为几何扭曲效果。

- **layerEffect(_:maxSampleOffset:isEnabled:)**：返回一个新视图，该视图将 `shader` 到 `self` 应用于由 `self` 创建的栅格图层，作为滤镜效果。

- **Shader**：指向 Metal 着色器库中函数的引用，以及其绑定的 uniform 参数值。

- **ShaderFunction**：指向 Metal 着色器库中函数的引用。

## 符合以下规范

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ShaderLibrary
crawled: 2025-12-02T17:37:52Z
---

# ShaderLibrary

**Structure**

A Metal shader library.

## Declaration

```swift
@dynamicMemberLookup struct ShaderLibrary
```

## Getting the default shader library

- **default**: The default shader library of the main (i.e. app) bundle.
- **bundle(_:)**: Returns the default shader library of the specified bundle.

## Creating a shader library

- **init(url:)**: Creates a new Metal shader library from the contents of `url`, which must be the location  of precompiled Metal library. Functions compiled from the returned library will only be cached as long as the returned library exists.
- **init(data:)**: Creates a new Metal shader library from `data`, which must be the contents of precompiled Metal library. Functions compiled from the returned library will only be cached as long as the returned library exists.

## Access shader functions

- **subscript(dynamicMember:)**: Returns a new shader function representing the stitchable MSL function called `name` in the default shader library.

## Subscripts

- **subscript(dynamicMember:)**: Returns a new shader function representing the stitchable MSL function in the library called `name`.

## Accessing Metal shaders

- **colorEffect(_:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter effect on the color of each pixel.
- **distortionEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a geometric distortion effect on the location of each pixel.
- **layerEffect(_:maxSampleOffset:isEnabled:)**: Returns a new view that applies `shader` to `self` as a filter on the raster layer created from `self`.
- **Shader**: A reference to a function in a Metal shader library, along with its bound uniform argument values.
- **ShaderFunction**: A reference to a function in a Metal shader library.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

