--- 来源：https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/full
抓取时间：2025-12-02T16:24:23Z

---

# full

**类型属性**

一种沉浸式样式，用于显示无边界内容，完全替换透视视频。

## 声明

```swift
static var full: FullImmersionStyle { get }
```

## 讨论

选择此沉浸式样式后，[onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) 闭包报告的沉浸量为 `1.0`。

使用 [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 场景修改器为 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 指定此样式。

使用此样式时，空间内容将完全遮蔽透视效果，仅保留用户的上肢。您可以通过将场景修改器 [upperLimbVisibility(_:)](../scene/upperLimbVisibility.zh-Hans.md) 应用于空间，或将等效于场景内视图的视图修改器应用于空间，来单独管理肢体可见性。

沉浸式样式会影响窗口与环境中虚拟对象的交互方式。在 `full` 沉浸式样式中，无论用户如何定位窗口或内容，窗口始终渲染在虚拟内容的前方。这有助于用户在关闭透视功能时避免丢失位于虚拟内容后面的窗口。

## 获取内置样式

- **automatic**：默认沉浸式样式。

- **mixed**：一种沉浸式样式，它将无边界内容与其他应用程序内容混合显示，并包含透视视频。

- **progressive**：一种沉浸式样式，它显示无边界内容，并部分替换透视视频。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/full
crawled: 2025-12-02T16:24:23Z
---

# full

**Type Property**

An immersion style that displays unbounded content that completely replaces passthrough video.

## Declaration

```swift
static var full: FullImmersionStyle { get }
```

## Discussion

When this immersion style is selected, the immersion amount reported by the closure of [onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) is `1.0`.

Use the [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to specify this style for an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md).

When using this style, the space’s content fully obscures passthrough except for the user’s upper limbs. You can manage limb visibility separately by applying the [upperLimbVisibility(_:)](../scene/upperLimbVisibility.zh-Hans.md) scene modifier to the space, or the view modifier equivalent to a view inside the scene.

The immersion style affects how windows interact with virtual objects in the environment. In `full` immersion, windows always render in front of virtual content, no matter how someone positions the window or the content. This helps people to avoid losing track of windows behind virtual content when passthrough is off.

## Getting built-in styles

- **automatic**: The default immersion style.
- **mixed**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.
- **progressive**: An immersion style that displays unbounded content that partially replaces passthrough video.

