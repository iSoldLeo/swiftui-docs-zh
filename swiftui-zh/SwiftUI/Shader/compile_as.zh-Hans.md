--- 来源：https://developer.apple.com/documentation/SwiftUI/Shader/compile(as:)

抓取时间：2025-12-03T06:34:02Z

---

# compile(as:)

**实例方法**

尝试异步编译着色器函数，以最大程度地减少首次用于渲染时出现卡顿的可能性。

## 声明

```swift
func compile(as type: Shader.UsageType) async throws
```

## 参数

- **type**：着色器最终的使用方式。

## 说明

每个着色器在可用于渲染之前都必须针对当前 GPU 进行编译。默认情况下，这会在首次使用时发生，但这可能会导致该帧因等待编译器而延迟，例如，在动画中造成可见的“卡顿”。

在每个着色器首次使用前调用此方法，可以提前完成必要的编译，从而消除首次实际使用时的延迟（前提是 `compile()` 在着色器首次使用前完成）。

为了确保编译成功，指定的使用类型必须与着色器最终的渲染方式相匹配，并且其当前参数值必须与渲染时使用的参数类型相匹配（但数组和数据大小可以为空）。

例如，要在应用程序启动时异步编译填充着色器：

```swift
Task {
    let shader = ShaderLibrary.example(.color(.clear), .float(0))
    try! await shader.compile(as: .shapeStyle)
}
```

此处，MSL 着色器函数 `example` 接受两个 uniform 参数：颜色和数值。使用着色器时，占位符值将被替换为实际值，在本例中用于填充圆形：

```swift
Circle().fill(
    ShaderLibrary.example(.color(.orange), .float(32)))
```


---
source: https://developer.apple.com/documentation/SwiftUI/Shader/compile(as:)
crawled: 2025-12-03T06:34:02Z
---

# compile(as:)

**Instance Method**

Attempts to asynchronously compile a shader function, to minimize the chance of stalling when it is first used for rendering.

## Declaration

```swift
func compile(as type: Shader.UsageType) async throws
```

## Parameters

- **type**: How the shader will eventually be used.

## Discussion

Before being available for rendering each shader must be compiled for the current GPU. By default this happens on first use, but that may cause that frame to be delayed waiting for the compiler, i.e. cause a visible “glitch” in animations.

Calling this method for each shader before it’s first used allows the necessary compilation to happen ahead of time, eliminating the delay on the first actual use (provided `compile()` completes before the first use of the shader).

For compilation to be successful the specified usage type must match how the shader is eventually used to render, and its current argument values must match the types of the arguments used when rendering (however array and data sizes may be empty).

For example, to compile a fill shader asynchronously when your app launches:

```swift
Task {
    let shader = ShaderLibrary.example(.color(.clear), .float(0))
    try! await shader.compile(as: .shapeStyle)
}
```

Here the MSL shader function `example` takes two uniform arguments: a color and a numeric value. The placeholder values are replaced with actual values when using the shader, in this case to fill a circle:

```swift
Circle().fill(
    ShaderLibrary.example(.color(.orange), .float(32)))
```



