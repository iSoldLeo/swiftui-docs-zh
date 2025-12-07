---
来源：https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionStyle/init(immersion:initialAmount:)
抓取时间：2025-12-04T11:28:50Z
---

# init(immersion:initialAmount:)

**Initializer**

一种沉浸式样式，可显示部分取代直通视频的无限制内容。

## 声明

```swift
init(immersion: ClosedRange<Double>, initialAmount: Double? = nil)
```

## 参数

- **immersion**：此样式实例使用的浸没范围。范围的下限值和上限值分别代表该样式的传送门效果所能覆盖的用户球形视野的最小值和最大值。下限值必须等于或大于`0.0`，小于上限值。上限值必须大于下限值，小于或等于`1.0`。
- **initialAmount**：该样式实例使用的初始浸入量。如果 `nil`，将使用系统默认值。该值必须在此样式定义的范围内。

## 讨论

沉浸样式会影响窗口与环境中虚拟对象的交互方式。在 `progressive`沉浸模式下，无论用户如何定位窗口或内容，窗口始终都会呈现在虚拟内容的前面。这可以帮助用户避免在关闭直通功能时丢失虚拟内容后面的窗口。

选择此沉浸样式时，[onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) 闭合所报告的沉浸量将在此样式所定义的沉浸量范围内。

使用[immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 场景修饰符为[ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 指定此样式：

```swift
@main
struct ImmersiveApp: App {
    @State private var immersionStyle: ImmersionStyle = .progressive(0.2...0.6, initial: 0.6)
    var body: some Scene {
        ImmersiveSpace { ... }
        .immersionStyle(selection: $immersionStyle, in: .progressive))
    }
}
```

该系统最初使用径向门户效果来取代部分视野中的穿透效果。人们可以通过转动数字表冠来交互式地调节传送门的大小，包括向下调节到应用程序所定义的最小沉浸量，向上调节到所定义的最大沉浸量。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionStyle/init(immersion:initialAmount:)
crawled: 2025-12-04T11:28:50Z
---

# init(immersion:initialAmount:)

**Initializer**

An immersion style that displays unbounded content that partially replaces passthrough video.

## Declaration

```swift
init(immersion: ClosedRange<Double>, initialAmount: Double? = nil)
```

## Parameters

- **immersion**: The range of immersion used for this instance of the style. The lower bound and upper bound value of the range represent the minimum and maximum amount of the spherical field of view of the user that can be covered by the portal effect of the style. The lower bound value must be equal to or greater than `0.0` and smaller than the upper bound. The upper bound value must be greater than the lower bound and smaller than or equal to `1.0`.
- **initialAmount**: The initial amount of immersion used for this instance of the style. If `nil`, a system default will be used. The value must be within the range defined by this style.

## Discussion

The immersion style affects how windows interact with virtual objects in the environment. In `progressive` immersion, windows always render in front of virtual content, no matter how someone positions the window or the content. This helps people avoid losing track of windows behind virtual content when passthrough is off.

When this immersion style is selected, the immersion amount reported by the closure of [onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) is within the range of the immersion that this style is defined with.

Use the [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to specify this style for an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md):

```swift
@main
struct ImmersiveApp: App {
    @State private var immersionStyle: ImmersionStyle = .progressive(0.2...0.6, initial: 0.6)
    var body: some Scene {
        ImmersiveSpace { ... }
        .immersionStyle(selection: $immersionStyle, in: .progressive))
    }
}
```

The system initially uses a radial portal effect that replaces passthrough in a portion of the field of view. People can interactively adjust the size of the portal by turning the Digital Crown, including down to a minimum amount of immersion defined by the app and up to the defined maximum amount of immersion.

