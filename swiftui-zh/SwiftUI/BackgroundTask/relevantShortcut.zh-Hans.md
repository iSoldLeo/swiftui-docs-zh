---
来源： https://developer.apple.com/documentation/SwiftUI/BackgroundTask/relevantShortcut
抓取时间： 2025-12-03T06:48:19Z
---

# 相关快捷方式

**类型属性**

用于定期捐赠相关 Siri 快捷方式的后台任务。

## 声明

```swift
static var relevantShortcut: BackgroundTask<Void, Void> { get }
```

## 更新意图和快捷方式

- **intentDidRun**：用于在 SiriKit intent 运行后更新应用程序的后台任务。


---
source: https://developer.apple.com/documentation/SwiftUI/BackgroundTask/relevantShortcut
crawled: 2025-12-03T06:48:19Z
---

# relevantShortcut

**Type Property**

A background task used to periodically donate relevant Siri shortcuts.

## Declaration

```swift
static var relevantShortcut: BackgroundTask<Void, Void> { get }
```

## Updating intents and shortcuts

- **intentDidRun**: A background task used to update your app after a SiriKit intent runs.

