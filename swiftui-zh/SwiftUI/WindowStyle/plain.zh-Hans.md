---
来源： https://developer.apple.com/documentation/SwiftUI/WindowStyle/plain
抓取时间： 2025-12-02T16:24:10Z
---

# plain

**类型属性**

普通窗口样式。

## 声明

```swift
static var plain: PlainWindowStyle { get }
```

## 讨论

与 [automatic](automatic.zh-Hans.md) 不同，在 visionOS 中，普通窗口不会使用玻璃背景，在 macOS 中，也不会使用窗口镀铬。如果你想对这些元素在窗口中的使用方式有更多控制，请使用此样式。

## 获取内置窗口样式

- **automatic**：默认窗口样式。
- **hiddenTitleBar**：一种隐藏窗口标题和标题栏后部区域的窗口样式，允许显示更多的窗口内容。
- **titleBar**：显示窗口标题栏部分的窗口样式。
- **volumetric**：一种窗口样式，用于创建三维体积窗口。


---
source: https://developer.apple.com/documentation/SwiftUI/WindowStyle/plain
crawled: 2025-12-02T16:24:10Z
---

# plain

**Type Property**

The plain window style.

## Declaration

```swift
static var plain: PlainWindowStyle { get }
```

## Discussion

Unlike [automatic](automatic.zh-Hans.md), a plain window does not receive a glass background in visionOS or window chrome in macOS. Use this style if you want more control over how these elements are used in your window.

## Getting built-in window styles

- **automatic**: The default window style.
- **hiddenTitleBar**: A window style which hides both the window’s title and the backing of the titlebar area, allowing more of the window’s content to show.
- **titleBar**: A window style which displays the title bar section of the window.
- **volumetric**: A window style that creates a 3D volumetric window.

