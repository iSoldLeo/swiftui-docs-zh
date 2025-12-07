--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/immersiveContentBrightness(_:)

抓取时间：2025-11-30T21:07:03Z

---

# immersiveContentBrightness(_:)

**实例方法**

设置沉浸式空间的内容亮度。

## 声明

```swift
nonisolated func immersiveContentBrightness(_ brightness: ImmersiveContentBrightness) -> some Scene

```

## 参数

- **brightness**：您偏好的内容亮度级别。

## 返回值

具有指定内容亮度的场景。

## 讨论

将 [ImmersiveContentBrightness](../ImmersiveContentBrightness.zh-Hans.md) 中定义的标准亮度级别之一，或使用 [custom(_:)](../ImmersiveContentBrightness/custom.zh-Hans.md) 方法创建的自定义亮度级别传递给此场景修改器，以设置 [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md) 中内容亮度的首选项。系统会考虑您设置的值，但可能无法完全满足特定的首选项。

当您这样做以创建适合视频播放的环境时，标准亮度值在大多数情况下都能提供良好的效果。为了进一步优化，您可以使用归一化值创建自定义亮度，该归一化值表示标准动态范围白色视频帧与播放器窗口周围背景之间的线性亮度比。

## 调整内容亮度

- **ImmersiveContentBrightness**：沉浸式空间的内容亮度。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/immersiveContentBrightness(_:)
crawled: 2025-11-30T21:07:03Z
---

# immersiveContentBrightness(_:)

**Instance Method**

Sets the content brightness of an immersive space.

## Declaration

```swift
nonisolated func immersiveContentBrightness(_ brightness: ImmersiveContentBrightness) -> some Scene

```

## Parameters

- **brightness**: The level of content brightness that you prefer.

## Return Value

A scene that has the specified content brightness.

## Discussion

Pass one of the standard brightness levels defined in [ImmersiveContentBrightness](../ImmersiveContentBrightness.zh-Hans.md) or a custom one that you create with the [custom(_:)](../ImmersiveContentBrightness/custom.zh-Hans.md) method to this scene modifier to set a preference for the content brightness in an [ImmersiveSpace](../ImmersiveSpace.zh-Hans.md). The system takes the value that you set into account, but might not be able to honor a specific preference.

When you do this to create an environment that’s suitable for video playback, the standard brightness values provide good results for most use cases. To optimize further, you can create a custom brightness using a normalized value that expresses the linear brightness ratio between a standard dynamic range white video frame and the background that surrounds the player window.



## Adjusting content brightness

- **ImmersiveContentBrightness**: The content brightness of an immersive space.

