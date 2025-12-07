---
来源： https://developer.apple.com/documentation/SwiftUI/ProgressViewStyleConfiguration/currentValueLabel-swift.property
抓取时间： 2025-12-03T05:43:52Z
---

# currentValueLabel

**实例属性**

描述进度视图当前值的视图。

## 声明

```swift
var currentValueLabel: ProgressViewStyleConfiguration.CurrentValueLabel?
```

## 讨论

如果`nil`，那么进度视图的值要么从周围的上下文中不言自明，要么是未知的，样式无需提供任何附加说明。

如果进度视图是使用`Progress` 实例定义的，则该标签等同于`localizedAdditionalDescription`。

## 配置当前值标签

- **ProgressViewStyleConfiguration.CurrentValueLabel**：描述进度视图当前值的分类型标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressViewStyleConfiguration/currentValueLabel-swift.property
crawled: 2025-12-03T05:43:52Z
---

# currentValueLabel

**Instance Property**

A view that describes the current value of a progress view.

## Declaration

```swift
var currentValueLabel: ProgressViewStyleConfiguration.CurrentValueLabel?
```

## Discussion

If `nil`, then the value of the progress view is either self-evident from the surrounding context or unknown, and the style does not need to provide any additional description.

If the progress view is defined using a `Progress` instance, then this label is equivalent to its `localizedAdditionalDescription`.

## Configuring the current value label

- **ProgressViewStyleConfiguration.CurrentValueLabel**: A type-erased label that describes the current value of a progress view.

