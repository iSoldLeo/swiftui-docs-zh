--- 来源：https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/subscript(dynamicMember:)-swift.type.subscript

抓取时间：2025-12-01T11:23:18Z

---

# subscript(dynamicMember:)

**类型下标**

返回一个新的着色器函数，该函数表示默认着色器库中名为 `name` 的可拼接 MSL 函数。

## 声明

```swift
static subscript(dynamicMember name: String) -> ShaderFunction { get }
```

## 概述

通常，此下标通过动态成员语法隐式使用，例如：

let fn = ShaderLibrary.myFunction

这将创建一个对名为 `myFunction()` 的 MSL 函数的引用。


---
source: https://developer.apple.com/documentation/SwiftUI/ShaderLibrary/subscript(dynamicMember:)-swift.type.subscript
crawled: 2025-12-01T11:23:18Z
---

# subscript(dynamicMember:)

**Type Subscript**

Returns a new shader function representing the stitchable MSL function called `name` in the default shader library.

## Declaration

```swift
static subscript(dynamicMember name: String) -> ShaderFunction { get }
```

## Overview

Typically this subscript is used implicitly via the dynamic member syntax, for example:

let fn = ShaderLibrary.myFunction

which creates a reference to the MSL function called `myFunction()`.

