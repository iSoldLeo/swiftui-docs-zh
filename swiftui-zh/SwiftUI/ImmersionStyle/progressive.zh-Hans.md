--- 来源：https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/progressive
抓取时间：2025-12-02T16:22:05Z

---

# progressive

**类型属性**

一种沉浸式样式，用于显示无边界内容，部分取代透视视频。

## 声明

```swift
static var progressive: ProgressiveImmersionStyle { get }
```

## 讨论

系统初始使用径向传送门效果，在部分视野范围内取代透视视频。用户可以通过旋转数码表冠来交互式地调整传送门的大小，从系统定义的最小沉浸度调整到传送门完全覆盖透视视频的位置。如果用户尝试将传送门大小减小到小于最小值，传送门会平滑地回弹到最小大小。门户在最大尺寸下的行为与 [full](full.zh-Hans.md) 沉浸式风格的行为一致，包括可配置的查看者上肢可见性。

选择此沉浸式风格后，[onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) 闭包报告的沉浸量将在此风格使用的沉浸范围内。

使用 [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 场景修改器为 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 指定此风格：

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

沉浸式风格会影响窗口与环境中虚拟对象的交互方式。在 `progressive` 沉浸式风格中，无论用户如何定位窗口或内容，窗口始终渲染在虚拟内容的前面。这有助于用户在关闭透视功能时避免丢失位于虚拟内容后面的窗口。

## 获取内置样式

- **automatic**：默认沉浸式样式。

- **full**：一种沉浸式样式，用于显示无边界内容，完全取代透传视频。

- **mixed**：一种沉浸式样式，用于显示无边界内容，并将其与其他应用内容混合显示，同时保留透传视频。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/progressive
crawled: 2025-12-02T16:22:05Z
---

# progressive

**Type Property**

An immersion style that displays unbounded content that partially replaces passthrough video.

## Declaration

```swift
static var progressive: ProgressiveImmersionStyle { get }
```

## Discussion

The system initially uses a radial portal effect that replaces passthrough in a portion of the field of view. People can interactively adjust the size of the portal by turning the Digital Crown, including down to a minimum amount of immersion defined by the system and up to the point where the portal fully covers passthrough. If someone tries to reduce the portal size below the minimum value, the portal smoothly bounces back to the minimum size. The portal’s behavior at the maximum size matches the behavior of the [full](full.zh-Hans.md) immersion style, including the configurable visibility of the viewer’s upper limbs.

When this immersion style is selected, the immersion amount reported by the closure of [onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) is within the range of the immersion that this style uses.

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

## Getting built-in styles

- **automatic**: The default immersion style.
- **full**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **mixed**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.

