--- 来源：https://developer.apple.com/documentation/SwiftUI/View/disabled(_:)

抓取时间：2025-11-30T21:17:45Z

---

# disabled(_:)

**实例方法**

添加一个条件，用于控制用户是否可以与此视图交互。

## 声明

```swift
nonisolated func disabled(_ disabled: Bool) -> some View

```

## 参数

- **disabled**：一个布尔值，用于确定用户是否可以与此视图交互。

## 返回值

一个用于控制用户是否可以与此视图交互的视图。

## 说明

视图层次结构中更高级别的视图可以覆盖您在此视图上设置的值。在以下示例中，按钮无法交互，因为外部的 `disabled(_:)` 修饰符覆盖了内部的修饰符：

```swift
HStack {
    Button(Text("Press")) {}
    .disabled(false)
}
.disabled(true)
```

## 管理视图交互

- **isEnabled**：一个布尔值，指示与此环境关联的视图是否允许用户交互。

- **interactionActivityTrackingTag(_:)**：设置用于跟踪交互性的标签。

- **invalidatableContent(_:)**：标记接收者，因为其内容可能无效。


---
source: https://developer.apple.com/documentation/SwiftUI/View/disabled(_:)
crawled: 2025-11-30T21:17:45Z
---

# disabled(_:)

**Instance Method**

Adds a condition that controls whether users can interact with this view.

## Declaration

```swift
nonisolated func disabled(_ disabled: Bool) -> some View

```

## Parameters

- **disabled**: A Boolean value that determines whether users can interact with this view.

## Return Value

A view that controls whether users can interact with this view.

## Discussion

The higher views in a view hierarchy can override the value you set on this view. In the following example, the button isn’t interactive because the outer `disabled(_:)` modifier overrides the inner one:

```swift
HStack {
    Button(Text("Press")) {}
    .disabled(false)
}
.disabled(true)
```

## Managing view interaction

- **isEnabled**: A Boolean value that indicates whether the view associated with this environment allows user interaction.
- **interactionActivityTrackingTag(_:)**: Sets a tag that you use for tracking interactivity.
- **invalidatableContent(_:)**: Mark the receiver as their content might be invalidated.

