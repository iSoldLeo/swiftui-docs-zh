---
来源： https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/windowArrangement
抓取时间： 2025-12-03T06:23:45Z
---

# 窗口排列

**类型属性**

用于安排应用程序所有窗口的命令。

## 声明

```swift
static let windowArrangement: CommandGroupPlacement
```

## 讨论

默认情况下，该组在 macOS 中包含以下命令：

- 将所有内容显示在前面

## Windows

- **singleWindowList**：用于放置描述和显示应用程序定义的任何窗口的命令。
- **windowList**：用于放置描述和显示应用程序打开的窗口的命令。
- **windowSize**：用于放置控制窗口大小的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandGroupPlacement/windowArrangement
crawled: 2025-12-03T06:23:45Z
---

# windowArrangement

**Type Property**

Placement for commands that arrange all of an app’s windows.

## Declaration

```swift
static let windowArrangement: CommandGroupPlacement
```

## Discussion

By default, this group includes the following command in macOS:

- Bring All to Front

## Windows

- **singleWindowList**: Placement for commands that describe and reveal any windows that the app defines.
- **windowList**: Placement for commands that describe and reveal the app’s open windows.
- **windowSize**: Placement for commands that control the size of the window.

