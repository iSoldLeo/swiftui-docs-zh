--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)-3q5nf

抓取时间：2025-12-03T05:43:42Z

---

# init(_:)

**Initializer**

创建一个进度视图，用于显示不确定的进度，其标签由字符串生成。

## 声明

```swift
nonisolated init<S>(_ title: S) where Label == Text, S : StringProtocol
```

## 参数

- **title**：描述当前任务的字符串。

## 说明

此初始化器会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并像 [init(verbatim:)](../Text/init_verbatim.zh-Hans.md) 一样处理标题。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。要使用本地化字符串键初始化进度视图，请使用接受 `LocalizedStringKey` 实例的相应初始化器。

## 创建不确定进度视图

- **init()**：创建一个用于显示不确定进度且不带标签的进度视图。

- **init(label:)**：创建一个用于显示不确定进度且带有自定义标签的进度视图。

- **init(_:)**：创建一个用于显示不确定进度且其标签由本地化字符串生成的进度视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)-3q5nf
crawled: 2025-12-03T05:43:42Z
---

# init(_:)

**Initializer**

Creates a progress view for showing indeterminate progress that generates its label from a string.

## Declaration

```swift
nonisolated init<S>(_ title: S) where Label == Text, S : StringProtocol
```

## Parameters

- **title**: A string that describes the task in progress.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the title similar to [init(verbatim:)](../Text/init_verbatim.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings. To initialize a progress view with a localized string key, use the corresponding initializer that takes a `LocalizedStringKey` instance.

## Creating an indeterminate progress view

- **init()**: Creates a progress view for showing indeterminate progress, without a label.
- **init(label:)**: Creates a progress view for showing indeterminate progress that displays a custom label.
- **init(_:)**: Creates a progress view for showing indeterminate progress that generates its label from a localized string.

