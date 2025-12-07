---
来源： https://developer.apple.com/documentation/SwiftUI/SettingsLink
抓取时间： 2025-12-02T17:20:53Z
---

# 设置链接

**Structure**

打开应用程序定义的 "设置 "场景的视图。

## 声明

```swift
struct SettingsLink<Label> where Label : View
```

## 概览

在 macOS 上，点击链接会打开场景窗口，如果已经打开，则会将其排在前面。

## 创建设置链接

- **init()**：创建带有默认系统标签的设置链接。
- **init(label:)**：创建带有自定义标签的设置链接。

## 支持类型

- **DefaultSettingsLinkLabel**：设置链接使用的默认标签。

## 管理设置窗口

- **Settings**：显示用于查看和修改应用程序设置的界面的场景。
- **OpenSettingsAction**：显示应用程序设置场景的操作。
- **openSettings**：存储在视图环境中的设置演示操作。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/SettingsLink
crawled: 2025-12-02T17:20:53Z
---

# SettingsLink

**Structure**

A view that opens the Settings scene defined by an app.

## Declaration

```swift
struct SettingsLink<Label> where Label : View
```

## Overview

On macOS, clicking on the link opens the window for the scene or orders it to the front if it is already open.

## Creating a settings link

- **init()**: Creates a settings link with the default system label.
- **init(label:)**: Creates a settings link with a custom label.

## Supporting types

- **DefaultSettingsLinkLabel**: The default label to use for a settings link.

## Managing a settings window

- **Settings**: A scene that presents an interface for viewing and modifying an app’s settings.
- **OpenSettingsAction**: An action that presents the settings scene for an app.
- **openSettings**: A Settings presentation action stored in a view’s environment.

## Conforms To

- View

