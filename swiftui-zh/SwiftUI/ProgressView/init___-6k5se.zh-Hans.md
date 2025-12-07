--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)-6k5se

抓取时间：2025-12-01T10:32:53Z

---

# init(_:)

**Initializer**

创建一个进度视图，用于显示不确定的进度，其标签由本地化字符串生成。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey) where Label == Text
```

## 参数

- **titleKey**：进度视图本地化标题的键，用于描述正在进行的任务。

## 说明

此初始化器会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并以类似于 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 的方式处理本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。要使用字符串变量初始化不确定进度视图，请使用接受 `StringProtocol` 实例的相应初始化器。

## 创建不确定进度视图

- **init()**：创建一个用于显示不确定进度且不带标签的进度视图。

- **init(label:)**：创建一个用于显示不确定进度且带有自定义标签的进度视图。

- **init(_:)**：创建一个用于显示不确定进度且标签由字符串生成的进度视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)-6k5se
crawled: 2025-12-01T10:32:53Z
---

# init(_:)

**Initializer**

Creates a progress view for showing indeterminate progress that generates its label from a localized string.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey) where Label == Text
```

## Parameters

- **titleKey**: The key for the progress view’s localized title that describes the task in progress.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings. To initialize a indeterminate progress view with a string variable, use the corresponding initializer that takes a `StringProtocol` instance.

## Creating an indeterminate progress view

- **init()**: Creates a progress view for showing indeterminate progress, without a label.
- **init(label:)**: Creates a progress view for showing indeterminate progress that displays a custom label.
- **init(_:)**: Creates a progress view for showing indeterminate progress that generates its label from a string.

