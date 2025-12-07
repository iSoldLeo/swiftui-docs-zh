--- 来源：https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/progressive(_:initialAmount:)

抓取时间：2025-12-03T05:33:25Z

---

# progressive(_:initialAmount:)

**类型方法**

一种沉浸式样式，用于显示无边界内容，部分替换透视视频。

## 声明

```swift
static func progressive(_ immersionRange: ClosedRange<Double>, initialAmount: Double? = nil) -> ProgressiveImmersionStyle
```

## 参数

- **immersionRange**：此样式实例使用的沉浸范围。范围的下限值和上限值分别表示用户球形视野中可被样式门户效果覆盖的最小和最大范围。下限值必须大于或等于 `0.0` 且小于上限值。上限值必须大于下限值，且小于或等于 `1.0`。

- **initialAmount**：此样式实例使用的初始沉浸度。如果为 `nil`，则使用系统默认值。该值必须在此样式定义的范围内。

## 讨论

沉浸样式会影响窗口与环境中虚拟对象的交互方式。在 `progressive` 沉浸样式下，无论窗口或内容如何定位，窗口始终渲染在虚拟内容的前面。这有助于用户在关闭透视功能时避免丢失位于虚拟内容后面的窗口。

选择此沉浸样式后，[onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) 闭包报告的沉浸度值将在此样式定义的沉浸度范围内。

使用场景修改器 [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 为 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 指定此样式：

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

系统初始使用径向门户效果，取代视野部分区域的透视效果。用户可以通过旋转数码表冠来交互式地调整门户的大小，包括缩小到应用程序定义的最小沉浸度，以及放大到应用程序定义的最大沉浸度。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/progressive(_:initialAmount:)
crawled: 2025-12-03T05:33:25Z
---

# progressive(_:initialAmount:)

**Type Method**

An immersion style that displays unbounded content that partially replaces passthrough video.

## Declaration

```swift
static func progressive(_ immersionRange: ClosedRange<Double>, initialAmount: Double? = nil) -> ProgressiveImmersionStyle
```

## Parameters

- **immersionRange**: The range of immersion used for this instance of the style. The lower bound and upper bound value of the range represent the minimum and maximum amount of the spherical field of view of the user that can be covered by the portal effect of the style. The lower bound value must be equal to or greater than `0.0` and smaller than the upper bound. The upper bound value must be greater than the lower bound and smaller than or equal to `1.0`.
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

