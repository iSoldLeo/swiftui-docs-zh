---
来源： https://developer.apple.com/documentation/SwiftUI/ProgressViewStyleConfiguration/label-swift.property
抓取时间： 2025-12-03T05:43:53Z
---

# 标签

**实例属性**

描述进度视图所代表任务的视图。

## 声明

```swift
var label: ProgressViewStyleConfiguration.Label?
```

## 讨论

如果`nil`，那么从周围的语境来看，任务是不言而喻的，文体不需要提供任何额外的说明。

如果进度视图是使用`Progress` 实例定义的，则该标签等同于其 `localizedDescription`。

## 配置标签

- **ProgressViewStyleConfiguration.Label**：描述进度视图所代表任务的分类型标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressViewStyleConfiguration/label-swift.property
crawled: 2025-12-03T05:43:53Z
---

# label

**Instance Property**

A view that describes the task represented by the progress view.

## Declaration

```swift
var label: ProgressViewStyleConfiguration.Label?
```

## Discussion

If `nil`, then the task is self-evident from the surrounding context, and the style does not need to provide any additional description.

If the progress view is defined using a `Progress` instance, then this label is equivalent to its `localizedDescription`.

## Configuring the label

- **ProgressViewStyleConfiguration.Label**: A type-erased label describing the task represented by the progress view.

