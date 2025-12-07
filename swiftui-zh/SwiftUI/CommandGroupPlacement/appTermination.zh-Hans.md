---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/appTermination
抓取时间： 2025-12-03T06:23:34Z
---

# 应用程序终止

**类型属性**

用于放置导致应用程序终止的命令。

## 声明

```swift
static let appTermination: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包含以下命令：

- 退出应用程序

## App 交互

- **appInfo**：用于放置提供有关应用程序、用户许可协议条款等信息的命令。
- **appSettings**：用于显示应用程序设置和首选项的命令。
- **appVisibility**：用于放置控制运行中应用程序可见性的命令。
- **systemServices**：用于放置公开其他应用程序所提供服务的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/appTermination
crawled: 2025-12-03T06:23:34Z
---

# appTermination

**Type Property**

Placement for commands that result in app termination.

## Declaration

```swift
static let appTermination: CommandGroupPlacement
```

## Discussion

By default, this group includes the following command in macOS:

- Quit App

## App interactions

- **appInfo**: Placement for commands that provide information about the app, the terms of the user’s license agreement, and so on.
- **appSettings**: Placement for commands that expose app settings and preferences.
- **appVisibility**: Placement for commands that control the visibility of running apps.
- **systemServices**: Placement for commands that expose services other apps provide.

