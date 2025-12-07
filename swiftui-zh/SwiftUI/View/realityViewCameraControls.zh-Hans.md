--- 来源：https://developer.apple.com/documentation/SwiftUI/View/realityViewCameraControls(_:)

抓取时间：2025-12-02T17:25:12Z

---

# realityViewCameraControls(_:)

**实例方法**

添加用于控制虚拟摄像机位置和方向的手势。

## 声明

```swift
@MainActor @preconcurrency func realityViewCameraControls(_ controls: CameraControls) -> some View

```

## 说明

您可以使用鼠标、触控板或 iOS 和 iPadOS 设备上的屏幕触摸来拖动虚拟摄像机，具体操作为：`.tilt`、`.pan`、`.orbit` 或 `.dolly`。

## 配置摄像机控件

- **realityViewCameraControls**：现实视图的摄像机控件。


---
source: https://developer.apple.com/documentation/SwiftUI/View/realityViewCameraControls(_:)
crawled: 2025-12-02T17:25:12Z
---

# realityViewCameraControls(_:)

**Instance Method**

Adds gestures that control the position and direction of a virtual camera.

## Declaration

```swift
@MainActor @preconcurrency func realityViewCameraControls(_ controls: CameraControls) -> some View

```

## Discussion

You can use a drag gesture from a mouse, trackpad, or screen touches with iOS and iPadOS devices to `.tilt`, `.pan`, `.orbit`, or `.dolly` a virtual camera.

## Configuring camera controls

- **realityViewCameraControls**: The camera controls for the reality view.

