---
来源： https://developer.apple.com/documentation/SwiftUI/Animatable/animatableData-6nydg
抓取时间： 2025-12-03T06:15:06Z
---

# animatableData

**实例属性**

要制作动画的数据。

## 声明

```swift
var animatableData: Self.AnimatableData { get set }
```

## 动画数据

- **Animatable()**：成员宏和扩展宏，当应用于结构体、类或枚举声明时，使用该宏所应用类型的现有可动画属性，合成符合`Animatable` 及其要求的`animatableData` 属性。
- **AnimatableIgnored()**：访问宏，用于标记从`animatableData` 合成中排除的类型属性：
- **AnimatableData**：定义动画数据的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Animatable/animatableData-6nydg
crawled: 2025-12-03T06:15:06Z
---

# animatableData

**Instance Property**

The data to animate.

## Declaration

```swift
var animatableData: Self.AnimatableData { get set }
```

## Animating data

- **Animatable()**: A member and extension macro that, when applied to a struct, class or enum declaration, synthesizes the conformance to `Animatable` and its requirement, the `animatableData` property using the existing animatable properties of the type this macro is applied to.
- **AnimatableIgnored()**: An accessor macro that marks a property of a type to be excluded from the `animatableData` synthesis:
- **AnimatableData**: The type defining the data to animate.

