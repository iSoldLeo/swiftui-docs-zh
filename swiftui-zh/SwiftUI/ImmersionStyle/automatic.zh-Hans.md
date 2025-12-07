--- 来源：https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/automatic

抓取时间：2025-12-02T21:41:36Z

---

# automatic

**类型属性**

默认沉浸式样式。

## 声明

```swift
static var automatic: AutomaticImmersionStyle { get }
```

## 讨论

如果您没有提供 [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) 场景修改器，系统将使用此样式作为 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md)。通常情况下，您无需显式指定 `automatic` 样式。

在 visionOS 系统中，默认情况下，系统使用 [mixed](mixed.zh-Hans.md) 沉浸式样式作为 `automatic` 样式；在 macOS 系统中，则使用 [full](full.zh-Hans.md) 沉浸式样式作为 `automatic` 样式。

## 获取内置样式

- **full**：一种沉浸式样式，用于显示无边界内容，完全取代透传视频。

- **mixed**：一种沉浸式样式，用于显示无边界内容，并与其他应用程序内容以及透传视频混合显示。

- **progressive**：一种沉浸式样式，用于显示无边界内容，部分取代透传视频。


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersionStyle/automatic
crawled: 2025-12-02T21:41:36Z
---

# automatic

**Type Property**

The default immersion style.

## Declaration

```swift
static var automatic: AutomaticImmersionStyle { get }
```

## Discussion

The system uses this style for an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) if you don’t provide an [immersionStyle(selection:in:)](../Scene/immersionStyle_selection_in.zh-Hans.md) scene modifier. You don’t typically specify the `automatic` style explicitly.

By default, on visionOS, the system uses the [mixed](mixed.zh-Hans.md) immersion style as the `automatic` style and for macOS the [full](full.zh-Hans.md) immersion style as the `automatic` style.

## Getting built-in styles

- **full**: An immersion style that displays unbounded content that completely replaces passthrough video.
- **mixed**: An immersion style that displays unbounded content intermixed with other app content, along with passthrough video.
- **progressive**: An immersion style that displays unbounded content that partially replaces passthrough video.

