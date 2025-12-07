--- 来源：https://developer.apple.com/documentation/SwiftUI/InterfaceOrientation
抓取时间：2025-12-02T17:46:03Z

---

# InterfaceOrientation

**Structure**

从用户视角来看，界面的方向。

## 声明

```swift
struct InterfaceOrientation
```

## 概述

默认情况下，设备预览以正向显示，方向为 [portrait](InterfaceOrientation/portrait.zh-Hans.md)。您可以通过调用 [previewInterfaceOrientation(_:)](View/previewInterfaceOrientation.zh-Hans.md) 修饰符来更改方向：

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewInterfaceOrientation(.landscapeRight)
    }
}
```

## 获取方向

- **portrait**：设备处于纵向模式，设备顶部朝上。

- **portraitUpsideDown**：设备处于竖屏模式，但屏幕方向颠倒。

- **landscapeLeft**：设备处于横屏模式，设备顶部位于左侧。

- **landscapeRight**：设备处于横屏模式，设备顶部位于右侧。

## 自定义预览

- **previewDevice(_:)**：覆盖预览设备。

- **PreviewDevice**：运行预览的模拟器设备。

- **previewLayout(_:)**：覆盖预览容器的大小。

- **previewInterfaceOrientation(_:)**：覆盖预览的方向。

## 符合以下标准

- CaseIterable

- Equatable

- Identifiable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/InterfaceOrientation
crawled: 2025-12-02T17:46:03Z
---

# InterfaceOrientation

**Structure**

The orientation of the interface from the user’s perspective.

## Declaration

```swift
struct InterfaceOrientation
```

## Overview

By default, device previews appear right side up, using orientation [portrait](InterfaceOrientation/portrait.zh-Hans.md). You can change the orientation with a call to the [previewInterfaceOrientation(_:)](View/previewInterfaceOrientation.zh-Hans.md) modifier:

```swift
struct CircleImage_Previews: PreviewProvider {
    static var previews: some View {
        CircleImage()
            .previewInterfaceOrientation(.landscapeRight)
    }
}
```

## Getting an orientation

- **portrait**: The device is in portrait mode, with the top of the device on top.
- **portraitUpsideDown**: The device is in portrait mode, but is upside down.
- **landscapeLeft**: The device is in landscape mode, with the top of the device on the left.
- **landscapeRight**: The device is in landscape mode, with the top of the device on the right.

## Customizing a preview

- **previewDevice(_:)**: Overrides the device for a preview.
- **PreviewDevice**: A simulator device that runs a preview.
- **previewLayout(_:)**: Overrides the size of the container for the preview.
- **previewInterfaceOrientation(_:)**: Overrides the orientation of the preview.

## Conforms To

- CaseIterable
- Equatable
- Identifiable
- Sendable
- SendableMetatype

