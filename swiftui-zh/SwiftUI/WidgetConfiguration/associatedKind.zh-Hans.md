---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/associatedKind(_:)
抓取时间： 2025-12-03T06:05:49Z
---

# associatedKind(_:)

**实例方法**

告诉系统基于相关性的 widget 可以替代基于时间线的 widget。

## 声明

```swift
@MainActor @preconcurrency func associatedKind(_ associatedKind: String?) -> some WidgetConfiguration

```

## 讨论

如果您提供基于时间轴的小工具和使用相关性线索的小工具，用户可以将时间轴小工具固定到智能堆栈中，这样智能堆栈中就会出现多个基于相关性线索的小工具实例，导致堆栈空间不足。要让智能堆栈通过使用相关性线索的小组件替换基于时间轴的小组件来显示最相关的小组件，请使用 `associatedKind(_:)` 将基于时间轴的小组件与相关性小组件配置关联起来。



有关 Apple Watch 智能堆栈中出现的 widget 的更多信息，请参阅 doc:Widget-Suggestions-In-Smart-Stacks。

- 参数：associatedKind：标识相关时间轴 widget 的字符串。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetConfiguration/associatedKind(_:)
crawled: 2025-12-03T06:05:49Z
---

# associatedKind(_:)

**Instance Method**

Tells the system that a relevance-based widget can replace a timeline-based widget.

## Declaration

```swift
@MainActor @preconcurrency func associatedKind(_ associatedKind: String?) -> some WidgetConfiguration

```

## Discussion

If you offer a timeline-based widget and a widget that uses relevance clues, a person could pin the timeline widget to the Smart Stack, and several instances of the relevance-based widget could appear in the Smart Stack, causing the stack to run out of space. To allow the Smart Stack to display the most relevant widgets by replacing the timeline-based widget with your widgets that use relevance clues, associate your timeline-based widget with relevance widget configuration using `associatedKind(_:)`.



For more information about widgets that appear in the Smart Stack on Apple Watch, refer to doc:Widget-Suggestions-In-Smart-Stacks.

- parameter: associatedKind: The string that identifies the associated timeline-based widget.

