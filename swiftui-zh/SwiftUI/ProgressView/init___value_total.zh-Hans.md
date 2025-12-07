--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:value:total:)

抓取时间：2025-12-01T10:32:56Z

---

# init(_:value:total:)

**Initializer**

创建一个进度视图，用于显示确定的进度，其标签由字符串生成。

## 声明

```swift
nonisolated init<S, V>(_ title: S, value: V?, total: V = 1.0) where Label == Text, CurrentValueLabel == EmptyView, S : StringProtocol, V : BinaryFloatingPoint
```

## 参数

- **title**：描述当前任务的字符串。

- **value**：任务目前已完成的进度，范围为 `0.0` 到 `total`，如果进度不确定，则为 `nil`。 **total**：代表任务完整范围的总量，即当 `value` 等于 `total` 时，任务完成。默认值为 `1.0`。

## 讨论

如果该值不是 `nil`，但超出 `0.0` 到 `total` 的范围，进度视图会将该值锁定在这些范围内，并四舍五入到最接近的边界值。`nil` 表示进度不确定，在这种情况下，进度视图会忽略 `total`。

此初始化器会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并且其标题的处理方式与 [init(verbatim:)](../Text/init_verbatim.zh-Hans.md) 类似。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。要使用本地化字符串键初始化确定性进度视图，请使用接受 `LocalizedStringKey` 实例的相应初始化器。

## 创建确定性进度视图

- **init(_:)**：创建一个进度视图，用于可视化给定的进度实例。

- **init(value:total:)**：创建一个进度视图，用于显示确定性进度。

- **init(value:total:label:)**：创建一个进度视图，用于显示具有自定义标签的确定性进度。

- **init(value:total:label:currentValueLabel:)**：创建一个进度视图，用于显示具有自定义标签的确定性进度。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:value:total:)
crawled: 2025-12-01T10:32:56Z
---

# init(_:value:total:)

**Initializer**

Creates a progress view for showing determinate progress that generates its label from a string.

## Declaration

```swift
nonisolated init<S, V>(_ title: S, value: V?, total: V = 1.0) where Label == Text, CurrentValueLabel == EmptyView, S : StringProtocol, V : BinaryFloatingPoint
```

## Parameters

- **title**: The string that describes the task in progress.
- **value**: The completed amount of the task to this point, in a range of `0.0` to `total`, or `nil` if the progress is indeterminate.
- **total**: The full amount representing the complete scope of the task, meaning the task is complete if `value` equals `total`. The default value is `1.0`.

## Discussion

If the value is non-`nil`, but outside the range of `0.0` through `total`, the progress view pins the value to those limits, rounding to the nearest possible bound. A value of `nil` represents indeterminate progress, in which case the progress view ignores `total`.

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the title similar to [init(verbatim:)](../Text/init_verbatim.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings. To initialize a determinate progress view with a localized string key, use the corresponding initializer that takes a `LocalizedStringKey` instance.

## Creating a determinate progress view

- **init(_:)**: Creates a progress view for visualizing the given progress instance.
- **init(value:total:)**: Creates a progress view for showing determinate progress.
- **init(value:total:label:)**: Creates a progress view for showing determinate progress, with a custom label.
- **init(value:total:label:currentValueLabel:)**: Creates a progress view for showing determinate progress, with a custom label.

