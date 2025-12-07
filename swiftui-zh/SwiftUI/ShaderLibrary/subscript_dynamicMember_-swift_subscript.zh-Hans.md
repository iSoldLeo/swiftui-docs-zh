--- 来源：https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/subscript(dynamicMember:)-swift.subscript

抓取时间：2025-12-03T06:34:09Z

---

# subscript(dynamicMember:)

**实例下标**

返回一个新的着色器函数，该函数表示库中名为 `name` 的可拼接 MSL 函数。

## 声明

```swift
subscript(dynamicMember name: String) -> ShaderFunction { get }
```

## 概述

通常，此下标通过动态成员语法隐式使用，例如：

let fn = ShaderLibrary.default.myFunction

这将创建一个对名为 `myFunction()` 的 MSL 函数的引用。


---
source: https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/subscript(dynamicMember:)-swift.subscript
crawled: 2025-12-03T06:34:09Z
---

# subscript(dynamicMember:)

**Instance Subscript**

Returns a new shader function representing the stitchable MSL function in the library called `name`.

## Declaration

```swift
subscript(dynamicMember name: String) -> ShaderFunction { get }
```

## Overview

Typically this subscript is used implicitly via the dynamic member syntax, for example:

let fn = ShaderLibrary.default.myFunction

which creates a reference to the MSL function called `myFunction()`.

