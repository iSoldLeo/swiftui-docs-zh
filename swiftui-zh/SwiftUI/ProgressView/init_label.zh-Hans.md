--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(label:)

抓取时间：2025-12-03T05:43:40Z

---

# init(label:)

**Initializer**

创建一个进度视图，用于显示不确定进度，并显示自定义标签。

## 声明

```swift
nonisolated init(@ViewBuilder label: () -> Label)
```

## 参数

- **label**：一个视图构建器，用于创建一个描述当前任务的视图。

## 创建不确定进度视图

- **init()**：创建一个进度视图，用于显示不确定进度，但不显示标签。

- **init(_:)**：创建一个进度视图，用于显示不确定进度，并根据本地化字符串生成标签。 - **init(_:)**：创建一个进度视图，用于显示不确定的进度，其标签由字符串生成。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(label:)
crawled: 2025-12-03T05:43:40Z
---

# init(label:)

**Initializer**

Creates a progress view for showing indeterminate progress that displays a custom label.

## Declaration

```swift
nonisolated init(@ViewBuilder label: () -> Label)
```

## Parameters

- **label**: A view builder that creates a view that describes the task in progress.

## Creating an indeterminate progress view

- **init()**: Creates a progress view for showing indeterminate progress, without a label.
- **init(_:)**: Creates a progress view for showing indeterminate progress that generates its label from a localized string.
- **init(_:)**: Creates a progress view for showing indeterminate progress that generates its label from a string.

