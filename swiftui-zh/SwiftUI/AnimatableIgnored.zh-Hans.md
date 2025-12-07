--- 来源：https://developer.apple.com/documentation/SwiftUI/AnimatableIgnored()

抓取时间：2025-12-01T11:04:14Z

---

# AnimatableIgnored()

**Macro**

一个访问器宏，用于标记要从 `animatableData` 合成中排除的类型属性：

## 声明

```swift
@attached(accessor, names: named(willSet)) macro AnimatableIgnored()
```

## 概述

```swift
@Animatable
struct CoolShape: Shape {
    var width: CGFloat
    var height: CGFloat
    @AnimatableIgnored var isVisible: Bool

    // ...
}
```

在上面的示例中，`CoolShape` 的 `isVisible` 属性将不会参与 `animatableData` 的合成。

## 数据动画

- **Animatable()**：成员和扩展宏，当应用于结构体、类或枚举声明时，它会使用应用此宏的类型中现有的可动画属性，合成对 `Animatable` 及其要求 `animatableData` 属性的符合性。

- **animatableData**：要动画化的数据。

- **AnimatableData**：定义要动画化的数据的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/AnimatableIgnored()
crawled: 2025-12-01T11:04:14Z
---

# AnimatableIgnored()

**Macro**

An accessor macro that marks a property of a type to be excluded from the `animatableData` synthesis:

## Declaration

```swift
@attached(accessor, names: named(willSet)) macro AnimatableIgnored()
```

## Overview

```swift
@Animatable
struct CoolShape: Shape {
    var width: CGFloat
    var height: CGFloat
    @AnimatableIgnored var isVisible: Bool

    // ...
}
```

In the above example, the `isVisible` property of `CoolShape` will not be participating in the synthesis of `animatableData`.

## Animating data

- **Animatable()**: A member and extension macro that, when applied to a struct, class or enum declaration, synthesizes the conformance to `Animatable` and its requirement, the `animatableData` property using the existing animatable properties of the type this macro is applied to.
- **animatableData**: The data to animate.
- **AnimatableData**: The type defining the data to animate.

