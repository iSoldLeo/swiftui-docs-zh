---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/systemServices
抓取时间： 2025-12-03T06:23:35Z
---

# 系统服务

**类型属性**

用于放置暴露其他应用程序提供的服务的命令。

## 声明

```swift
static let systemServices: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包含以下命令：

- 服务子菜单（自动管理）

## 应用程序交互

- **appInfo**：用于放置提供应用程序信息、用户许可协议条款等信息的命令。
- **appSettings**：用于显示应用程序设置和首选项的命令。
- **appTermination**：放置会导致应用程序终止的命令。
- **appVisibility**：用于放置控制运行中应用程序可见性的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/systemServices
crawled: 2025-12-03T06:23:35Z
---

# systemServices

**Type Property**

Placement for commands that expose services other apps provide.

## Declaration

```swift
static let systemServices: CommandGroupPlacement
```

## Discussion

By default, this group includes the following command in macOS:

- Services submenu (managed automatically)

## App interactions

- **appInfo**: Placement for commands that provide information about the app, the terms of the user’s license agreement, and so on.
- **appSettings**: Placement for commands that expose app settings and preferences.
- **appTermination**: Placement for commands that result in app termination.
- **appVisibility**: Placement for commands that control the visibility of running apps.

