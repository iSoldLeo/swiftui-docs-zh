---
来源： https://developer.apple.com/documentation/swiftui/dialogseverity
抓取时间： 2025-12-03T06:02:42Z
---

# DialogSeverity

**Structure**

警报或确认对话框的严重性。

## 声明

```swift
struct DialogSeverity
```

## 概览

您可以使用对话框严重性来表示人们在与对话框交互时需要格外小心，例如当从对话框中执行的操作会永久删除数据时。

## 获取严重性

- **automatic**：默认的对话框严重性。显示错误的警报将使用 `.critical`，所有其他警报将使用 `.standard`。
- **standard**：严重程度，表示显示对话框的目的是向用户提供信息。
- **critical**：表示应格外注意对话框的严重性，例如当所采取的操作可能导致意外数据丢失时。

## 符合

- 可等同
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/swiftui/dialogseverity
crawled: 2025-12-03T06:02:42Z
---

# DialogSeverity

**Structure**

The severity of an alert or confirmation dialog.

## Declaration

```swift
struct DialogSeverity
```

## Overview

You can use dialog severity to indicate that people need to take extra care when interacting with the dialog, like when an action taken from the dialog permanently deletes data.

## Getting severities

- **automatic**: The default dialog severity. Alerts that present an error will use `.critical` and all others will use `.standard`.
- **standard**: A severity that indicates the dialog is being displayed for the purpose of presenting information to the user.
- **critical**: A severity that indicates extra attention should be given to the dialog, for example when unexpected data loss may occur as a result of the action taken.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

