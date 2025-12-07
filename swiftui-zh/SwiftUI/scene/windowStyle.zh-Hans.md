--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/windowStyle(_:)

抓取时间：2025-11-30T21:06:06Z

---

# windowStyle(_:)

**实例方法**

设置此场景创建的窗口的样式。

## 声明

```swift
nonisolated func windowStyle<S>(_ style: S) -> some Scene where S : WindowStyle

```

## 创建窗口

- **WindowGroup**：呈现一组结构相同的窗口的场景。

- **Window**：在单个窗口中呈现其内容的场景。

- **UtilityWindow**：为应用程序主场景的内容提供辅助功能的专用窗口场景。

- **WindowStyle**：窗口外观和交互的规范。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/windowStyle(_:)
crawled: 2025-11-30T21:06:06Z
---

# windowStyle(_:)

**Instance Method**

Sets the style for windows created by this scene.

## Declaration

```swift
nonisolated func windowStyle<S>(_ style: S) -> some Scene where S : WindowStyle

```

## Creating windows

- **WindowGroup**: A scene that presents a group of identically structured windows.
- **Window**: A scene that presents its content in a single, unique window.
- **UtilityWindow**: A specialized window scene that provides secondary utility to the content of the main scenes of an application.
- **WindowStyle**: A specification for the appearance and interaction of a window.

