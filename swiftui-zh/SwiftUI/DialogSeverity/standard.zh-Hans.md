---
来源： https://developer.apple.com/documentation/SwiftUI/DialogSeverity/standard
抓取时间： 2025-12-03T06:02:01Z
---

# 标准

**类型属性**

严重程度，表示显示对话框的目的是向用户提供信息。

## 声明

```swift
static let standard: DialogSeverity
```

## 获取严重程度

- **automatic**：默认对话框严重性。显示错误的警报将使用 `.critical`，所有其他警报将使用 `.standard`。
- **critical**：表示应格外注意对话框的严重性，例如当所采取的操作可能导致意外数据丢失时。


---
source: https://developer.apple.com/documentation/SwiftUI/DialogSeverity/standard
crawled: 2025-12-03T06:02:01Z
---

# standard

**Type Property**

A severity that indicates the dialog is being displayed for the purpose of presenting information to the user.

## Declaration

```swift
static let standard: DialogSeverity
```

## Getting severities

- **automatic**: The default dialog severity. Alerts that present an error will use `.critical` and all others will use `.standard`.
- **critical**: A severity that indicates extra attention should be given to the dialog, for example when unexpected data loss may occur as a result of the action taken.

