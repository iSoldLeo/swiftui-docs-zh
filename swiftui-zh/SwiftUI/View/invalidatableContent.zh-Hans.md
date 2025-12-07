--- 来源：https://developer.apple.com/documentation/SwiftUI/View/invalidatableContent(_:)

抓取时间：2025-12-02T17:32:42Z

---

# invalidatableContent(_:)

**实例方法**

将接收器标记为内容可能失效。

## 声明

```swift
nonisolated func invalidatableContent(_ invalidatable: Bool = true) -> some View

```

## 参数

- **invalidatable**：接收器内容是否可能失效。

## 说明

使用此修饰符来注释显示基于当前数据状态的值的视图，这些值可能会因用户交互等原因而失效。

当环境中存在 `RedactionReasons.invalidated` 时，视图的外观将发生变化。

在交互式组件中，从用户与组件上的控件交互到显示新的时间线更新期间，视图将失效。

## 管理视图交互

- **disabled(_:)**：添加一个条件，用于控制用户是否可以与此视图交互。

- **isEnabled**：一个布尔值，指示与此环境关联的视图是否允许用户交互。

- **interactionActivityTrackingTag(_:)**：设置一个用于跟踪交互性的标签。


---
source: https://developer.apple.com/documentation/SwiftUI/View/invalidatableContent(_:)
crawled: 2025-12-02T17:32:42Z
---

# invalidatableContent(_:)

**Instance Method**

Mark the receiver as their content might be invalidated.

## Declaration

```swift
nonisolated func invalidatableContent(_ invalidatable: Bool = true) -> some View

```

## Parameters

- **invalidatable**: Whether the receiver content might be invalidated.

## Discussion

Use this modifier to annotate views that display values that are derived from the current state of your data and might be invalidated in response of, for example, user interaction.

The view will change its appearance when `RedactionReasons.invalidated` is present in the environment.

In an interactive widget a view is invalidated from the moment the user interacts with a control on the widget to the moment when a new timeline update has been presented.

## Managing view interaction

- **disabled(_:)**: Adds a condition that controls whether users can interact with this view.
- **isEnabled**: A Boolean value that indicates whether the view associated with this environment allows user interaction.
- **interactionActivityTrackingTag(_:)**: Sets a tag that you use for tracking interactivity.

