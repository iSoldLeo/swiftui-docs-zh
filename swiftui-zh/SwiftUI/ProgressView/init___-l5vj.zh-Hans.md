--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)-l5vj

抓取时间：2025-12-01T10:32:55Z

---

# init(_:)

**Initializer**

创建一个进度视图，用于可视化给定的进度实例。

## 声明

```swift
nonisolated init(_ progress: Progress) where Label == EmptyView, CurrentValueLabel == EmptyView
```

## 说明

进度视图使用给定进度实例的 `localizedDescription` 生成默认标签。

## 创建确定性进度视图

- **init(value:total:)**：创建一个用于显示确定性进度的进度视图。

- **init(_:value:total:)**：创建一个用于显示确定性进度的进度视图，该视图的标签由字符串生成。

- **init(value:total:label:)**：创建一个进度视图，用于显示确定的进度，并带有自定义标签。

- **init(value:total:label:currentValueLabel:)**：创建一个进度视图，用于显示确定的进度，并带有自定义标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)-l5vj
crawled: 2025-12-01T10:32:55Z
---

# init(_:)

**Initializer**

Creates a progress view for visualizing the given progress instance.

## Declaration

```swift
nonisolated init(_ progress: Progress) where Label == EmptyView, CurrentValueLabel == EmptyView
```

## Discussion

The progress view synthesizes a default label using the `localizedDescription` of the given progress instance.

## Creating a determinate progress view

- **init(value:total:)**: Creates a progress view for showing determinate progress.
- **init(_:value:total:)**: Creates a progress view for showing determinate progress that generates its label from a string.
- **init(value:total:label:)**: Creates a progress view for showing determinate progress, with a custom label.
- **init(value:total:label:currentValueLabel:)**: Creates a progress view for showing determinate progress, with a custom label.

