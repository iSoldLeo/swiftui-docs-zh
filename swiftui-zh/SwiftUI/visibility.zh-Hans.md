---
来源： https://developer.apple.com/documentation/swiftui/visibility
抓取时间： 2025-12-03T05:37:13Z
---

# 可见性

**Enumeration**

用户界面元素的可见性，根据平台、当前上下文和其他因素自动选择。

## 声明

```swift
@frozen enum Visibility
```

## 概览

例如，可以使用 [listRowSeparator(_:edges:)](View/listRowSeparator___edges.zh-Hans.md) 配置列表行分隔符的首选可见性。

## 获取可见性选项

- **Visibility.automatic**：根据接受可见性配置的组件的策略，元素可能可见或隐藏。
- **Visibility.visible**：该元素可能是可见的。
- **Visibility.hidden**：该元素可能被隐藏。

## 隐藏系统元素

- **labelsHidden()**：隐藏该视图中包含的任何控件的标签。
- **labelsVisibility(_:)**：控制此视图中包含的任何控件的标签的可见性。
- **labelsVisibility**：由 [labelsVisibility(_:)](View/labelsVisibility.zh-Hans.md) 设置的标签可见性。
- **menuIndicator(_:)**：设置此视图中控件的菜单指示器可见性。
- **statusBarHidden(_:)**：设置状态栏的可见性。
- **persistentSystemOverlays(_:)**：设置状态栏的可见性：设置覆盖应用程序的非临时系统视图的首选可见性。

## 符合

- 比特可复制
- CaseIterable
- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/visibility
crawled: 2025-12-03T05:37:13Z
---

# Visibility

**Enumeration**

The visibility of a UI element, chosen automatically based on the platform, current context, and other factors.

## Declaration

```swift
@frozen enum Visibility
```

## Overview

For example, the preferred visibility of list row separators can be configured using the [listRowSeparator(_:edges:)](View/listRowSeparator___edges.zh-Hans.md).

## Getting visibility options

- **Visibility.automatic**: The element may be visible or hidden depending on the policies of the component accepting the visibility configuration.
- **Visibility.visible**: The element may be visible.
- **Visibility.hidden**: The element may be hidden.

## Hiding system elements

- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **labelsVisibility(_:)**: Controls the visibility of labels of any controls contained within this view.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](View/labelsVisibility.zh-Hans.md).
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **statusBarHidden(_:)**: Sets the visibility of the status bar.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

