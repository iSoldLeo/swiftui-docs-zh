---
来源： https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionStyle/init()
抓取时间： 2025-12-04T11:28:49Z
---

# init()

**Initializer**

一种沉浸式风格，可显示部分取代直通式视频的无限制内容。

## 声明

```swift
init()
```

## 讨论

该系统最初使用的是径向传送门效果，它可以取代部分视野中的透视效果。人们可以通过转动数字皇冠来交互式地调整传送门的大小，直至传送门完全取代透视效果。后者与[full](../ImmersionStyle/full.zh-Hans.md)沉浸式风格的行为相匹配，包括观众上肢的可配置可见度。

选择该沉浸样式时，[onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) 闭合所报告的沉浸量将在该样式所定义的沉浸量范围内。

使用[immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 场景修饰符为[ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 指定此样式：

```swift
@main
struct ImmersiveApp: App {
    @State private var immersionStyle: ImmersionStyle = .progressive
    var body: some Scene {
        ImmersiveSpace { ... }
        .immersionStyle(selection: $immersionStyle, in: .progressive))
    }
}
```

沉浸式风格会影响窗口与环境中虚拟对象的交互方式。在 `progressive`沉浸模式下，无论用户如何定位窗口或内容，窗口总是呈现在虚拟内容的前面。这可以帮助用户避免在关闭直通功能时丢失虚拟内容后面的窗口。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressiveImmersionStyle/init()
crawled: 2025-12-04T11:28:49Z
---

# init()

**Initializer**

An immersion style that displays unbounded content that partially replaces passthrough video.

## Declaration

```swift
init()
```

## Discussion

The system initially uses a radial portal effect that replaces passthrough in a portion of the field of view. People can interactively adjust the size of the portal by turning the Digital Crown, up to the point where the portal fully replaces passthrough. The latter matches the behavior of the [full](../ImmersionStyle/full.zh-Hans.md) immersion style, including the configurable visibility of the viewer’s upper limbs.

When this immersion style is selected, the immersion amount reported by the closure of [onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) is within the range of the immersion that this style is defined with.

Use the [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to specify this style for an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md):

```swift
@main
struct ImmersiveApp: App {
    @State private var immersionStyle: ImmersionStyle = .progressive
    var body: some Scene {
        ImmersiveSpace { ... }
        .immersionStyle(selection: $immersionStyle, in: .progressive))
    }
}
```

The immersion style affects how windows interact with virtual objects in the environment. In `progressive` immersion, windows always render in front of virtual content, no matter how someone positions the window or the content. This helps people avoid losing track of windows behind virtual content when passthrough is off.

