---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/appInfo
抓取时间： 2025-12-03T06:23:32Z
---

# 应用信息

**类型属性**

用于放置提供应用程序信息、用户许可协议条款等信息的命令。

### 声明

```swift
static let appInfo: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包含以下命令：

- 关于应用程序

## 应用程序交互

- **appSettings**：用于显示应用程序设置和首选项的命令的位置。
- **appTermination**：放置会导致应用程序终止的命令。
- **appVisibility**：控制运行中应用程序可见性的命令的位置。
- **systemServices**：用于放置公开其他应用程序所提供服务的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/appInfo
crawled: 2025-12-03T06:23:32Z
---

# appInfo

**Type Property**

Placement for commands that provide information about the app, the terms of the user’s license agreement, and so on.

## Declaration

```swift
static let appInfo: CommandGroupPlacement
```

## Discussion

By default, this group includes the following command in macOS:

- About App

## App interactions

- **appSettings**: Placement for commands that expose app settings and preferences.
- **appTermination**: Placement for commands that result in app termination.
- **appVisibility**: Placement for commands that control the visibility of running apps.
- **systemServices**: Placement for commands that expose services other apps provide.

