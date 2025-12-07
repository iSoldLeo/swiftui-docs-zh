---
来源： https://developer.apple.com/documentation/swiftui/volumetricwindowstyle
抓取时间： 2025-12-05T21:08:21Z
---

# 体积窗口样式

**Structure**

一种创建三维体积窗口的窗口样式。

## 声明

```swift
struct VolumetricWindowStyle
```

## 概览

使用 [volumetric](WindowStyle/volumetric.zh-Hans.md) 构建此样式：

```swift
WindowGroup {
    ContentView()
}
.windowStyle(.volumetric)
```

## 创建窗口样式

- **init()**

## 支持类型

- **DefaultWindowStyle**：默认窗口样式。
- **HiddenTitleBarWindowStyle**：一种隐藏窗口标题和标题栏后部区域的窗口样式，允许显示更多的窗口内容。
- **PlainWindowStyle**：普通窗口样式。
- **TitleBarWindowStyle**：显示窗口标题栏部分的窗口样式。

## 符合

- 窗口样式


---
source: https://developer.apple.com/documentation/swiftui/volumetricwindowstyle
crawled: 2025-12-05T21:08:21Z
---

# VolumetricWindowStyle

**Structure**

A window style that creates a 3D volumetric window.

## Declaration

```swift
struct VolumetricWindowStyle
```

## Overview

Use [volumetric](WindowStyle/volumetric.zh-Hans.md) to construct this style:

```swift
WindowGroup {
    ContentView()
}
.windowStyle(.volumetric)
```

## Creating the window style

- **init()**

## Supporting types

- **DefaultWindowStyle**: The default window style.
- **HiddenTitleBarWindowStyle**: A window style which hides both the window’s title and the backing of the titlebar area, allowing more of the window’s content to show.
- **PlainWindowStyle**: The plain window style.
- **TitleBarWindowStyle**: A window style which displays the title bar section of the window.

## Conforms To

- WindowStyle

