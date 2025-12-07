--- 来源：https://developer.apple.com/documentation/SwiftUI/View/continuityDevicePicker(isPresented:onDidConnect:)

抓取时间：2025-11-30T21:08:32Z

---

#continuityDevicePicker(isPresented:onDidConnect:)

**实例方法**

`continuityDevicePicker` 用于通过按钮或其他方式激活，发现并连接附近的连续互通设备。在 tvOS 上，选中此方法后，会显示一个全屏的连续互通设备选择器。当满足特定条件时，模态视图会尽可能覆盖 `self` 的屏幕。

## 声明

```swift
@MainActor @preconcurrency func continuityDevicePicker(isPresented: Binding<Bool>, onDidConnect: ((AVContinuityDevice?) -> Void)? = nil) -> some View

```

## 参数

- **isPresented**：一个 `Binding` 参数，用于控制是否显示模态视图。

- **onDidConnect**：一个闭包，当选择器成功连接 AVContinuityDevice 时执行，如果用户取消则返回 nil。

## 显示媒体

- **CameraView**：一个 SwiftUI 视图，用于渲染视频流或图像快照。

- **NowPlayingView**：一个显示系统“正在播放”界面的视图，以便用户可以控制音频。

- **VideoPlayer**：一个显示播放器内容和用于控制播放的原生用户界面的视图。

- **cameraAnchor(isActive:)**：指定用作 Apple Vision Pro 2D Persona 流虚拟摄像机的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/continuityDevicePicker(isPresented:onDidConnect:)
crawled: 2025-11-30T21:08:32Z
---

# continuityDevicePicker(isPresented:onDidConnect:)

**Instance Method**

A `continuityDevicePicker` should be used to discover and connect nearby continuity device through a button interface or other form of activation. On tvOS, this presents a fullscreen continuity device picker experience when selected. The modal view covers as much the screen of `self` as possible when a given condition is true.

## Declaration

```swift
@MainActor @preconcurrency func continuityDevicePicker(isPresented: Binding<Bool>, onDidConnect: ((AVContinuityDevice?) -> Void)? = nil) -> some View

```

## Parameters

- **isPresented**: A `Binding` to whether the modal view is presented.
- **onDidConnect**: A closure executed when the picker successfully, connects AVContinuityDevice or nil if cancelled by a user.

## Displaying media

- **CameraView**: A SwiftUI view into which a video stream or an image snapshot is rendered.
- **NowPlayingView**: A view that displays the system’s Now Playing interface so that the user can control audio.
- **VideoPlayer**: A view that displays content from a player and a native user interface to control playback.
- **cameraAnchor(isActive:)**: Specifies the view that should act as the virtual camera for Apple Vision Pro 2D Persona stream.

