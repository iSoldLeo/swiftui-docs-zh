--- 来源：https://developer.apple.com/documentation/SwiftUI/View/cameraAnchor(isActive:)

抓取时间：2025-12-02T17:45:26Z

---

# cameraAnchor(isActive:)

**实例方法**

指定用于 Apple Vision Pro 2D Persona 流的虚拟摄像头视图。

## 声明

```swift
@MainActor func cameraAnchor(isActive: Bool = true) -> some View

```

## 参数

- **isActive**：摄像头锚点是否处于活动状态。

如果您希望在应用中创建多个可作为锚点的视图，可以使用此值来确保一次只有一个摄像头锚点处于活动状态。

## 讨论

VisionOS 应用可以使用此修饰符来指定用于创建用户 Persona 2D 流的虚拟摄像头的位置。例如，视频会议应用可能会将此修饰符添加到通话期间显示其他参与者的视图中。这样，当 visionOS 上的参与者看向该视图时，他们的 Persona 角色就会与其他参与者进行眼神交流。锚点将位于修改后的视图中心。

```swift
ExampleAppVideoView()
    .cameraAnchor()
```

您可能需要创建多个带有锚点的视图，然后仅激活获得焦点的视图。

```swift
struct ExampleSelfPreviewWhenFocusedView: View {
   @Environment(\.isFocused) var isFocused: Bool

   var body: some View {
       ExampleAppVideoView()
        #if os(visionOS)
            .cameraAnchor(isActive: isFocused)
        #endif
   }
}
```

## 显示媒体

- **CameraView**：用于渲染视频流或图像快照的 SwiftUI 视图。

- **NowPlayingView**：用于显示系统“正在播放”界面的视图，以便用户可以控制音频。

- **VideoPlayer**：用于显示播放器内容和用于控制播放的原生用户界面的视图。

- **continuityDevicePicker(isPresented:onDidConnect:)**：应使用 `continuityDevicePicker` 通过按钮界面或其他激活方式发现并连接附近的连续互通设备。在 tvOS 上，选中后会显示全屏连续互通设备选择器。当满足特定条件时，模态视图会尽可能覆盖 `self` 的屏幕。


---
source: https://developer.apple.com/documentation/SwiftUI/View/cameraAnchor(isActive:)
crawled: 2025-12-02T17:45:26Z
---

# cameraAnchor(isActive:)

**Instance Method**

Specifies the view that should act as the virtual camera for Apple Vision Pro 2D Persona stream.

## Declaration

```swift
@MainActor func cameraAnchor(isActive: Bool = true) -> some View

```

## Parameters

- **isActive**: Whether or not the camera anchor is active.

You can use this value to ensure that only one camera anchor is active at a time if you want to create multiple views that could act as the anchor in your app.

## Discussion

This modifier can be used by visionOS apps to specify the placement of the virtual camera used to create a 2D stream of the user’s Persona. For example, a video conferencing app might add this modifier to the view that shows the other participants during a call. Then when the participant on visionOS looks at that view their Persona will make eye contact with the other participants on the call. The anchor will be at the center of the modified View.

```swift
ExampleAppVideoView()
    .cameraAnchor()
```

You might want to create multiple views with an anchor and then only activate the one that has focus.

```swift
struct ExampleSelfPreviewWhenFocusedView: View {
   @Environment(\.isFocused) var isFocused: Bool

   var body: some View {
       ExampleAppVideoView()
        #if os(visionOS)
            .cameraAnchor(isActive: isFocused)
        #endif
   }
}
```



## Displaying media

- **CameraView**: A SwiftUI view into which a video stream or an image snapshot is rendered.
- **NowPlayingView**: A view that displays the system’s Now Playing interface so that the user can control audio.
- **VideoPlayer**: A view that displays content from a player and a native user interface to control playback.
- **continuityDevicePicker(isPresented:onDidConnect:)**: A `continuityDevicePicker` should be used to discover and connect nearby continuity device through a button interface or other form of activation. On tvOS, this presents a fullscreen continuity device picker experience when selected. The modal view covers as much the screen of `self` as possible when a given condition is true.

