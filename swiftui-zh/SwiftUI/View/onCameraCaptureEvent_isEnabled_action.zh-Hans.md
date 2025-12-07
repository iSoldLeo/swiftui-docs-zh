--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onCameraCaptureEvent(isEnabled:action:)

抓取时间：2025-12-02T17:42:31Z

---

# onCameraCaptureEvent(isEnabled:action:)

**实例方法**

用于注册由系统拍摄事件触发的操作。

## 声明

```swift
@MainActor @preconcurrency func onCameraCaptureEvent(isEnabled: Bool = true, action: @escaping (AVCaptureEvent) -> Void) -> some View

```

## 参数

- **isEnabled**：一个布尔值，指示拍摄事件是否触发提供的操作。如果您的应用程序无法或不会响应操作回调，请将此值设置为 `false`，以避免出现无法交互的按钮或 UI 元素。

- **action**：当主事件或辅助事件触发时调用的事件处理程序。

## 讨论

事件是否会发送给应用程序取决于当前系统状态。后台运行的应用程序不会接收事件，此外，事件只会发送给正在使用摄像头的应用程序。

如果来自某个来源的事件开始，则来自其他来源的事件将被忽略，直到第一个事件结束或被取消。

此 API 仅适用于媒体捕获用例。

## 响应捕获事件

- **onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)**：用于注册由系统捕获事件触发的操作。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onCameraCaptureEvent(isEnabled:action:)
crawled: 2025-12-02T17:42:31Z
---

# onCameraCaptureEvent(isEnabled:action:)

**Instance Method**

Used to register an action triggered by system capture events.

## Declaration

```swift
@MainActor @preconcurrency func onCameraCaptureEvent(isEnabled: Bool = true, action: @escaping (AVCaptureEvent) -> Void) -> some View

```

## Parameters

- **isEnabled**: A boolean value indicating whether capture events trigger the provided action or not. Set this value to `false` when your application cannot or will not respond to the action callbacks to avoid non-interactive buttons or UI elements.
- **action**: An event handler called when either the primary or secondary events are triggered.

## Discussion

Events may or may not be sent to applications based on the current system state. Backgrounded applications will not receive events, additionally events will only be sent to applications that are actively using the camera.

If an event from one source begins, then events from other sources will be ignored until the first event ends or is cancelled.

This API is for media capture use cases only.

## Responding to capture events

- **onCameraCaptureEvent(isEnabled:primaryAction:secondaryAction:)**: Used to register actions triggered by system capture events.

