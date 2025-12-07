---
来源： https://developer.apple.com/documentation/SwiftUI/DialogSeverity/critical
抓取时间： 2025-12-03T06:02:02Z
---

# 关键

**类型属性**

严重程度，表示应格外注意对话框，例如当所采取的操作可能导致意外数据丢失时。

## 声明

```swift
static let critical: DialogSeverity
```

## 讨论

在 macOS 上，严重程度为临界的对话框会显示一个大的警告符号，并叠加应用程序图标。

## 获取严重程度

- **automatic**：默认对话框严重性。显示错误的警报将使用 `.critical`，所有其他警报将使用 `.standard`。
- **standard**：严重性，表示显示对话框的目的是向用户提供信息。


---
source: https://developer.apple.com/documentation/SwiftUI/DialogSeverity/critical
crawled: 2025-12-03T06:02:02Z
---

# critical

**Type Property**

A severity that indicates extra attention should be given to the dialog, for example when unexpected data loss may occur as a result of the action taken.

## Declaration

```swift
static let critical: DialogSeverity
```

## Discussion

On macOS, a dialog with critical severity will display a large caution symbol with the app icon as an overlay.

## Getting severities

- **automatic**: The default dialog severity. Alerts that present an error will use `.critical` and all others will use `.standard`.
- **standard**: A severity that indicates the dialog is being displayed for the purpose of presenting information to the user.

