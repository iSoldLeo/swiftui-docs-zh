--- 来源：https://developer.apple.com/documentation/swiftui/compositorcontent/persistentsystemoverlays(_:)

抓取时间：2025-12-01T11:21:51Z

---

# persistentSystemOverlays(_:)

**实例方法**

设置覆盖在应用上的非瞬态系统视图的首选可见性。

## 声明

```swift
nonisolated func persistentSystemOverlays(_ visibility: Visibility) -> some CompositorContent

```

## 参数

- **visibility**：指示覆盖在应用上的非瞬态系统视图可见性的值。

## 说明

使用此修饰符可以影响应用中系统覆盖层的外观。其行为因平台而异。对于 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md)，它会影响主屏幕指示器。

受影响的非瞬态系统视图可能包括但不限于：

- 主页指示器。

- SharePlay 指示器。

- iPad 上的多任务控制按钮和画中画功能。


---
source: https://developer.apple.com/documentation/swiftui/compositorcontent/persistentsystemoverlays(_:)
crawled: 2025-12-01T11:21:51Z
---

# persistentSystemOverlays(_:)

**Instance Method**

Sets the preferred visibility of the non-transient system views overlaying the app.

## Declaration

```swift
nonisolated func persistentSystemOverlays(_ visibility: Visibility) -> some CompositorContent

```

## Parameters

- **visibility**: A value that indicates the visibility of the non-transient system views overlaying the app.

## Discussion

Use this modifier to influence the appearance of system overlays in your app. The behavior varies by platform. For an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md), it affects the Home indicator.



Affected non-transient system views can include, but are not limited to:

- The Home indicator.
- The SharePlay indicator.
- The Multitasking Controls button and Picture in Picture on iPad.

