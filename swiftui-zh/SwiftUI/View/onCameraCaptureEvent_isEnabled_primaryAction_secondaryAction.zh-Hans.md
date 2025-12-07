--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)

抓取时间：2025-11-30T21:27:37Z

---

# onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)

**实例方法**

用于注册由系统拍摄事件触发的操作。

## 声明

```swift
@MainActor @preconcurrency func onCameraCaptureEvent(isEnabled: Bool = true, primaryAction: @escaping (AVCaptureEvent) -> Void, secondaryAction: @escaping (AVCaptureEvent) -> Void) -> some View

```

## 参数

- **isEnabled**：一个布尔值，指示拍摄事件是否触发提供的操作。当您的应用程序无法或不会响应操作回调时，请将此值设置为 `false`，以避免出现无法交互的按钮或 UI 元素。

- **primaryAction**：主拍摄事件触发时调用的事件处理程序。

- **secondaryAction**：辅助拍摄事件触发时调用的事件处理程序。

## 讨论

事件是否会发送给应用程序取决于当前系统状态。后台运行的应用程序不会接收事件，此外，事件只会发送给正在使用摄像头的应用程序。

此 API 仅适用于媒体拍摄用例。

## 响应拍摄事件

- **onCameraCaptureEvent(isEnabled:action:)**：用于注册由系统拍摄事件触发的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)
crawled: 2025-11-30T21:27:37Z
---

# onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)

**Instance Method**

Used to register actions triggered by system capture events.

## Declaration

```swift
@MainActor @preconcurrency func onCameraCaptureEvent(isEnabled: Bool = true, primaryAction: @escaping (AVCaptureEvent) -> Void, secondaryAction: @escaping (AVCaptureEvent) -> Void) -> some View

```

## Parameters

- **isEnabled**: A boolean value indicating whether capture events trigger the provided actions or not. Set this value to `false` when your application cannot or will not respond to the action callbacks to avoid non-interactive buttons or UI elements.
- **primaryAction**: An event handler called when a primary capture event is triggered.
- **secondaryAction**: An event handler called when a secondary capture event is triggered.

## Discussion

Events may or may not be sent to applications based on the current system state. Backgrounded applications will not receive events, additionally events will only be sent to applications that are actively using the camera.

This API is for media capture use cases only.

## Responding to capture events

- **onCameraCaptureEvent(isEnabled:action:)**: Used to register an action triggered by system capture events.

