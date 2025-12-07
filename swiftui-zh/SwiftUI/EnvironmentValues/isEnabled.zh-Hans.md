---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isEnabled
抓取时间： 2025-12-02T17:32:41Z
---

# isEnabled

**实例属性**

布尔值，表示与此环境相关的视图是否允许用户交互。

## 声明

```swift
var isEnabled: Bool { get set }
```

## 讨论

默认值为 `true`。

## 管理视图交互

- **disabled(_:)**：添加控制用户能否与该视图交互的条件。
- **interactionActivityTrackingTag(_:)**：设置用于跟踪交互性的标记。
- **invalidatableContent(_:)**：将接收者标记为其内容可能失效。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isEnabled
crawled: 2025-12-02T17:32:41Z
---

# isEnabled

**Instance Property**

A Boolean value that indicates whether the view associated with this environment allows user interaction.

## Declaration

```swift
var isEnabled: Bool { get set }
```

## Discussion

The default value is `true`.

## Managing view interaction

- **disabled(_:)**: Adds a condition that controls whether users can interact with this view.
- **interactionActivityTrackingTag(_:)**: Sets a tag that you use for tracking interactivity.
- **invalidatableContent(_:)**: Mark the receiver as their content might be invalidated.

