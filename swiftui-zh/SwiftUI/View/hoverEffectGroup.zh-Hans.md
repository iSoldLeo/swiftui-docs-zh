--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hoverEffectGroup()

抓取时间：2025-12-02T17:42:03Z

---

# hoverEffectGroup()

**实例方法**

为所有子视图上定义的效果添加一个隐式的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，这样，当鼠标悬停在该视图或其任何子视图上时，添加到子视图的所有效果都会作为一个整体激活。

## 声明

```swift
nonisolated func hoverEffectGroup() -> some View

```

## 返回值

一个激活给定悬停组以及添加到子视图的所有效果的视图。

## 说明

当视图及其子视图上定义的所有效果应该同时激活时，可以使用此修饰符。在以下示例中，将鼠标悬停在视图上的任意位置将激活添加到 `Text` 和背景视图的 `hoverEffect`：

```swift
struct EffectView: View {
    var effectGroup: HoverEffectGroup?

    var body: some View {
        HStack {
            Image(systemName: "exclamationmark.triangle.fill")
            Text("12 Issues")
                .hoverEffect { effect, isActive, _ in
                    effect.opacity(isActive ? 1 : 0.5)
                }
        }
        .padding()
        .background {
            Capsule()
                .fill(.yellow)
                .hoverEffect { effect, isActive, _ in
                    effect.opacity(isActive ? 0.25 : 0.1)
                }
        }
        .hoverEffectGroup()
   }
}
```

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：为此视图应用悬停效果。

- **HoverEffect**：指针悬停在视图上时应用的效果。

- **hoverEffect(_:in:isEnabled:)**：为此视图应用悬停效果，并可选择将其添加到 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)。

- **hoverEffect(in:isEnabled:body:)**：为此视图应用由给定闭包描述的悬停效果。

- **CustomHoverEffect**：一种类型，表示当指针悬停在视图上或有人查看视图时，视图应如何变化。

- **ContentHoverEffect**：一种 `CustomHoverEffect`，使用闭包在悬停时对视图应用效果。

- **HoverEffectGroup**：描述一组同时激活的效果。

- **hoverEffectGroup(_:)**：向所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在悬停于此视图或任何子视图时激活该组效果。

- **hoverEffectGroup(id:in:behavior:)**：向所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在悬停于此视图或任何子视图时激活该组效果。

- **GroupHoverEffect**：一个用于激活指定效果组的 `CustomHoverEffect`。

- **HoverEffectContent**：一种类型，用于描述视图在特定悬停效果阶段的效果。

- **EmptyHoverEffectContent**：一个空的基础效果，可用于构建其他效果。

- **handPointerBehavior(_:)**：设置用户与视图交互时手形指针的行为。

- **HandPointerBehavior**：一种可在用户与视图交互时应用于手形指针的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hoverEffectGroup()
crawled: 2025-12-02T17:42:03Z
---

# hoverEffectGroup()

**Instance Method**

Adds an implicit [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.

## Declaration

```swift
nonisolated func hoverEffectGroup() -> some View

```

## Return Value

A view that activates the given hover group, as well as all effects added to subviews.

## Discussion

You use this modifier when all effects defined on a view and its subviews should activate together. In the following example hovering anywhere over the view will activate the `hoverEffect`s added to the `Text` and the background view:

```swift
struct EffectView: View {
    var effectGroup: HoverEffectGroup?

    var body: some View {
        HStack {
            Image(systemName: "exclamationmark.triangle.fill")
            Text("12 Issues")
                .hoverEffect { effect, isActive, _ in
                    effect.opacity(isActive ? 1 : 0.5)
                }
        }
        .padding()
        .background {
            Capsule()
                .fill(.yellow)
                .hoverEffect { effect, isActive, _ in
                    effect.opacity(isActive ? 0.25 : 0.1)
                }
        }
        .hoverEffectGroup()
   }
}
```

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **CustomHoverEffect**: A type that represents how a view should change when a pointer hovers over a view, or when someone looks at the view.
- **ContentHoverEffect**: A `CustomHoverEffect` that applies effects to a view on hover using a closure.
- **HoverEffectGroup**: Describes a grouping of effects that activate together.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(id:in:behavior:)**: Adds a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **GroupHoverEffect**: A `CustomHoverEffect` that activates a named group of effects.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

