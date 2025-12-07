--- 来源：https://developer.apple.com/documentation/SwiftUI/ShaderFunction/dynamicallyCall(withArguments:)

抓取时间：2025-12-01T11:23:14Z

---

# dynamicallyCall(withArguments:)

**实例方法**

通过将提供的参数值应用于引用的函数来返回一个新的着色器。

## 声明

```swift
func dynamicallyCall(withArguments args: [Shader.Argument]) -> Shader
```

## 讨论

通常，此下标通过函数调用语法隐式使用，例如：

let shader = ShaderLibrary.default.myFunction(.float(42))

这将创建一个着色器，并将值 `42` 传递给 `myFunction()` 的第一个未绑定参数。

## 配置函数

- **library**：存储该函数的着色器库。

- **name**：库中着色器函数的名称。


---
source: https://developer.apple.com/documentation/SwiftUI/ShaderFunction/dynamicallyCall(withArguments:)
crawled: 2025-12-01T11:23:14Z
---

# dynamicallyCall(withArguments:)

**Instance Method**

Returns a new shader by applying the provided argument values to the referenced function.

## Declaration

```swift
func dynamicallyCall(withArguments args: [Shader.Argument]) -> Shader
```

## Discussion

Typically this subscript is used implicitly via function-call syntax, for example:

let shader = ShaderLibrary.default.myFunction(.float(42))

which creates a shader passing the value `42` to the first unbound parameter of `myFunction()`.

## Configuring a function

- **library**: The shader library storing the function.
- **name**: The name of the shader function in the library.

