--- 来源：https://developer.apple.com/documentation/SwiftUI/View/persistentSystemOverlays(_:)

抓取时间：2025-11-30T21:17:44Z

---

# persistentSystemOverlays(_:)

**实例方法**

设置覆盖在应用上的非瞬态系统视图的首选可见性。

## 声明

```swift
nonisolated func persistentSystemOverlays(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：一个指示覆盖在应用上的非瞬态系统视图可见性的值。

## 说明

使用此修饰符可以影响应用中系统覆盖层的外观。其行为因平台而异。

在 iOS 中，以下示例会隐藏所有持久系统覆盖层。在 visionOS 2 及更高版本中，如果场景通过 SharePlay 共享，或者根本没有共享，则会隐藏 SharePlay 指示器。屏幕共享期间，指示器始终可见。将可见性设置为 `hidden` 时，主屏幕指示器不会在没有用户明确意图的情况下显示。对于 [WindowGroup](../WindowGroup.zh-Hans.md)，修饰符会影响窗口边框的可见性。对于 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md)，修饰符会影响主屏幕指示器。

```swift
struct ImmersiveView: View {
    var body: some View {
        Text("Maximum immersion")
            .persistentSystemOverlays(.hidden)
    }
}
```

受影响的非瞬态系统视图包括但不限于：

- 主屏幕指示器。

- SharePlay 指示器。

- iPad 上的多任务控制按钮和画中画功能。

## 隐藏系统元素

- **labelsHidden()**：隐藏此视图中包含的任何控件的标签。

- **labelsVisibility(_:)**：控制此视图中包含的任何控件的标签的可见性。

- **labelsVisibility**：由 [labelsVisibility(_:)](labelsVisibility.zh-Hans.md) 设置的标签可见性。

- **menuIndicator(_:)**：设置此视图中控件的菜单指示器可见性。

- **statusBarHidden(_:)**：设置状态栏的可见性。

- **Visibility**：UI 元素的可见性，根据平台、当前上下文和其他因素自动选择。


---
source: https://developer.apple.com/documentation/SwiftUI/View/persistentSystemOverlays(_:)
crawled: 2025-11-30T21:17:44Z
---

# persistentSystemOverlays(_:)

**Instance Method**

Sets the preferred visibility of the non-transient system views overlaying the app.

## Declaration

```swift
nonisolated func persistentSystemOverlays(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: A value that indicates the visibility of the non-transient system views overlaying the app.

## Discussion

Use this modifier to influence the appearance of system overlays in your app. The behavior varies by platform.

In iOS, the following example hides every persistent system overlay. In visionOS 2 and later, the SharePlay Indicator hides if the scene is shared through SharePlay, or not shared at all. During screen sharing, the indicator always remains visible. The Home indicator doesn’t appear without specific user intent when you set visibility to `hidden`. For a [WindowGroup](../WindowGroup.zh-Hans.md), the modifier affects the visibility of the window chrome. For an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md), it affects the Home indicator.

```swift
struct ImmersiveView: View {
    var body: some View {
        Text("Maximum immersion")
            .persistentSystemOverlays(.hidden)
    }
}
```



Affected non-transient system views can include, but are not limited to:

- The Home indicator.
- The SharePlay indicator.
- The Multitasking Controls button and Picture in Picture on iPad.

## Hiding system elements

- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **labelsVisibility(_:)**: Controls the visibility of labels of any controls contained within this view.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](labelsVisibility.zh-Hans.md).
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **statusBarHidden(_:)**: Sets the visibility of the status bar.
- **Visibility**: The visibility of a UI element, chosen automatically based on the platform, current context, and other factors.

