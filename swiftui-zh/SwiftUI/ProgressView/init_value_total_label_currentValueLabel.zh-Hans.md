--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(value:total:label:currentValueLabel:)

抓取时间：2025-12-01T10:32:58Z

---

# init(value:total:label:currentValueLabel:)

**Initializer**

创建一个进度视图，用于显示确定的进度，并带有自定义标签。

## 声明

```swift
nonisolated init<V>(value: V?, total: V = 1.0, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel) where V : BinaryFloatingPoint
```

## 参数

- **value**：任务目前已完成的进度，范围为 `0.0` 到 `total`，如果进度不确定，则为 `nil`。

- **total**：代表任务完整范围的总量，即当 `value` 等于 `total` 时，任务完成。默认值为 `1.0`。

- **label**：用于创建描述任务进行中状态的视图的视图构建器。

- **currentValueLabel**：用于创建描述任务完成进度的视图构建器。

## 讨论

如果该值不是 `nil`，但超出 `0.0` 到 `total` 的范围，则进度视图会将该值限制在这些范围内，并四舍五入到最接近的边界值。 `nil` 值表示进度不确定，在这种情况下，进度视图会忽略 `total`。

## 创建确定进度视图

- **init(_:)**：创建一个进度视图，用于可视化给定的进度实例。

- **init(value:total:)**：创建一个进度视图，用于显示确定进度。

- **init(_:value:total:)**：创建一个进度视图，用于显示确定进度，其标签由字符串生成。

- **init(value:total:label:)**：创建一个进度视图，用于显示确定进度，并带有自定义标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(value:total:label:currentValueLabel:)
crawled: 2025-12-01T10:32:58Z
---

# init(value:total:label:currentValueLabel:)

**Initializer**

Creates a progress view for showing determinate progress, with a custom label.

## Declaration

```swift
nonisolated init<V>(value: V?, total: V = 1.0, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel) where V : BinaryFloatingPoint
```

## Parameters

- **value**: The completed amount of the task to this point, in a range of `0.0` to `total`, or `nil` if the progress is indeterminate.
- **total**: The full amount representing the complete scope of the task, meaning the task is complete if `value` equals `total`. The default value is `1.0`.
- **label**: A view builder that creates a view that describes the task in progress.
- **currentValueLabel**: A view builder that creates a view that describes the level of completed progress of the task.

## Discussion

If the value is non-`nil`, but outside the range of `0.0` through `total`, the progress view pins the value to those limits, rounding to the nearest possible bound. A value of `nil` represents indeterminate progress, in which case the progress view ignores `total`.

## Creating a determinate progress view

- **init(_:)**: Creates a progress view for visualizing the given progress instance.
- **init(value:total:)**: Creates a progress view for showing determinate progress.
- **init(_:value:total:)**: Creates a progress view for showing determinate progress that generates its label from a string.
- **init(value:total:label:)**: Creates a progress view for showing determinate progress, with a custom label.

