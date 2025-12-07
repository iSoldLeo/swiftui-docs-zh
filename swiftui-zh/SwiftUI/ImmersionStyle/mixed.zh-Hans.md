--- 来源：https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/mixed

抓取时间：2025-12-02T16:24:21Z

---

# mixed

**类型属性**

一种沉浸式样式，用于显示与应用其他内容混合的无边界内容，以及透传视频。

## 声明

```swift
static var mixed: MixedImmersionStyle { get }
```

## 讨论

选择此沉浸式样式后，[onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) 闭包报告的沉浸量为 `0.0`。

使用 [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 场景修改器为 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 指定此样式。但是，如果您未指定沉浸式样式，则此为默认样式。

沉浸式风格会影响窗口与环境中虚拟对象的交互方式。在 `mixed` 沉浸式风格中，虚拟对象会遮挡其后方窗口的部分或全部内容。同样，窗口也会遮挡其后方的虚拟对象。

## 获取内置风格

- **automatic**：默认沉浸式风格。

- **full**：一种显示无边界内容的沉浸式风格，完全取代透传视频。

- **progressive**：一种显示无边界内容的沉浸式风格，部分取代透传视频。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/mixed
crawled: 2025-12-02T16:24:21Z
---

# mixed

**Type Property**

An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.

## Declaration

```swift
static var mixed: MixedImmersionStyle { get }
```

## Discussion

When this immersion style is selected, the immersion amount reported by the closure of [onImmersionChange(initial:_:)](../View/onImmersionChange_initial.zh-Hans.md) is `0.0`.

Use the [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier to specify this style for an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md). However, this is the default immersion style if you don’t specify one.

The immersion style affects how windows interact with virtual objects in the environment. In `mixed` immersion, a virtual object obscures part or all of a window that’s behind the object. Similarly, a window obscures a virtual object that’s behind the window.

## Getting built-in styles

- **automatic**: The default immersion style.
- **full**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **progressive**: An immersion style that displays unbounded content that partially replaces passthrough video.

