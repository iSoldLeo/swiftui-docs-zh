--- 来源：https://developer.apple.com/documentation/SwiftUI/WindowStyle
抓取时间：2025-12-02T17:21:00Z

---

# WindowStyle

**Protocol**

窗口外观和交互的规范。

## 声明

```swift
protocol WindowStyle
```

## 获取内置窗口样式

- **automatic**：默认窗口样式。

- **hiddenTitleBar**：隐藏窗口标题和标题栏背景，从而显示更多窗口内容的窗口样式。

- **plain**：纯文本窗口样式。

- **titleBar**：显示窗口标题栏部分的窗口样式。

- **volumetric**：一种创建 3D 立体窗口的窗口样式。

## 支持的类型

- **DefaultWindowStyle**：默认窗口样式。

- **HiddenTitleBarWindowStyle**：一种隐藏窗口标题和标题栏背景，从而显示更多窗口内容的窗口样式。

- **PlainWindowStyle**：普通窗口样式。

- **TitleBarWindowStyle**：一种显示窗口标题栏部分的窗口样式。

- **VolumetricWindowStyle**：一种创建 3D 立体窗口的窗口样式。

## 创建窗口

- **WindowGroup**：一种呈现一组结构相同的窗口的场景。

- **Window**：一个将内容呈现在单个独立窗口中的场景。

- **UtilityWindow**：一个专门的窗口场景，为应用程序的主场景内容提供辅助功能。

- **windowStyle(_:)**：设置此场景创建的窗口的样式。

## 符合规范的类型

- DefaultWindowStyle

- HiddenTitleBarWindowStyle

- PlainWindowStyle

- TitleBarWindowStyle

- VolumetricWindowStyle


---
source: https://developer.apple.com/documentation/SwiftUI/WindowStyle
crawled: 2025-12-02T17:21:00Z
---

# WindowStyle

**Protocol**

A specification for the appearance and interaction of a window.

## Declaration

```swift
protocol WindowStyle
```

## Getting built-in window styles

- **automatic**: The default window style.
- **hiddenTitleBar**: A window style which hides both the window’s title and the backing of the titlebar area, allowing more of the window’s content to show.
- **plain**: The plain window style.
- **titleBar**: A window style which displays the title bar section of the window.
- **volumetric**: A window style that creates a 3D volumetric window.

## Supporting types

- **DefaultWindowStyle**: The default window style.
- **HiddenTitleBarWindowStyle**: A window style which hides both the window’s title and the backing of the titlebar area, allowing more of the window’s content to show.
- **PlainWindowStyle**: The plain window style.
- **TitleBarWindowStyle**: A window style which displays the title bar section of the window.
- **VolumetricWindowStyle**: A window style that creates a 3D volumetric window.

## Creating windows

- **WindowGroup**: A scene that presents a group of identically structured windows.
- **Window**: A scene that presents its content in a single, unique window.
- **UtilityWindow**: A specialized window scene that provides secondary utility to the content of the main scenes of an application.
- **windowStyle(_:)**: Sets the style for windows created by this scene.

## Conforming Types

- DefaultWindowStyle
- HiddenTitleBarWindowStyle
- PlainWindowStyle
- TitleBarWindowStyle
- VolumetricWindowStyle

