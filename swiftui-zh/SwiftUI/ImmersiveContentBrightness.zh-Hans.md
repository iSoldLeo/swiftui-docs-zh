--- 来源：https://developer.apple.com/documentation/SwiftUI/ImmersiveContentBrightness
抓取时间：2025-12-02T17:21:59Z

---

# ImmersiveContentBrightness

**Structure**

沉浸式空间的内容亮度。

## 声明

```swift
struct ImmersiveContentBrightness
```

## 概述

使用此类型的值作为 [immersiveContentBrightness(_:)](scene/immersiveContentBrightness.zh-Hans.md) 场景修改器的输入，以指示 [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) 的环境内容亮度。

当您创建适合视频播放的环境时，请使用标准亮度值，例如 [bright](ImmersiveContentBrightness/bright.zh-Hans.md)、[dim](ImmersiveContentBrightness/dim.zh-Hans.md) 或 [dark](ImmersiveContentBrightness/dark.zh-Hans.md)，以便在大多数使用场景下获得良好的效果。为了进一步优化，您可以使用归一化值创建自定义亮度，该归一化值表示标准动态范围白色视频帧与播放器窗口周围背景之间的线性亮度比。

## 获取亮度级别

- **automatic**：默认内容亮度。

- **dark**：较暗的内容亮度。

- **dim**：较暗的内容亮度。

- **bright**：较亮的内容亮度。

- **custom(_:)**：使用自定义值创建内容亮度。

## 调整内容亮度

- **immersiveContentBrightness(_:)**：设置沉浸式空间的内容亮度。

## 符合以下标准

- Equatable


---
source: https://developer.apple.com/documentation/SwiftUI/ImmersiveContentBrightness
crawled: 2025-12-02T17:21:59Z
---

# ImmersiveContentBrightness

**Structure**

The content brightness of an immersive space.

## Declaration

```swift
struct ImmersiveContentBrightness
```

## Overview

Use a value of this type as an input to the [immersiveContentBrightness(_:)](scene/immersiveContentBrightness.zh-Hans.md) scene modifier to indicate the ambient content brightness of an [ImmersiveSpace](ImmersiveSpace.zh-Hans.md).

When you do this to create an environment that’s suitable for video playback, use one of the standard brightness values like [bright](ImmersiveContentBrightness/bright.zh-Hans.md), [dim](ImmersiveContentBrightness/dim.zh-Hans.md), or [dark](ImmersiveContentBrightness/dark.zh-Hans.md) to provide good results for most use cases. To optimize further, you can create a custom brightness using a normalized value that expresses the linear brightness ratio between a standard dynamic range white video frame and the background that surrounds the player window.

## Getting brightness levels

- **automatic**: The default content brightness.
- **dark**: A dark content brightness.
- **dim**: A dimmed content brightness.
- **bright**: A bright content brightness.
- **custom(_:)**: Creates a content brightness with a custom value.

## Adjusting content brightness

- **immersiveContentBrightness(_:)**: Sets the content brightness of an immersive space.

## Conforms To

- Equatable

