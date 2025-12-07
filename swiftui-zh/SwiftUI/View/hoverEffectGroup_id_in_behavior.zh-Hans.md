--- 来源：https://developer.apple.com/documentation/SwiftUI/View/hoverEffectGroup(id:in:behavior:)

抓取时间：2025-12-02T17:42:05Z

---

# hoverEffectGroup(id:in:behavior:)

**实例方法**

向所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停于此视图或任何子视图时激活该效果组。

## 声明

```swift
nonisolated func hoverEffectGroup(id: String? = nil, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup) -> some View

```

## 参数

- **id**：可选参数，用于指定效果组的 ID。如果提供此参数，则该效果组将通过 ID 和命名空间的组合进行唯一标识。

- **namespace**：标识该效果组的命名空间。如果 `nil` 为真，则此修饰符无效。

- **behavior**：效果相对于组中其他效果的行为方式。

## 返回值

与同一组中其他效果匹配的新效果。

## 说明

当视图及其子视图上定义的所有效果需要同时激活时，可以使用此修饰符。在以下示例中，将鼠标悬停在视图上的任意位置将激活添加到 `Text` 和背景视图的 `hoverEffect`，以及其他视图添加到该组的任何效果：

```swift
struct EffectView: View {
    @Namespace var namespace

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
        .hoverEffectGroup(in: namespace)
    }
}
```

效果组通过组合 `id` 和 `namespace` 参数来唯一标识。如果未提供 `id`，则效果将仅由 `namespace` 标识。当创建使用多个相关组的效果时，提供 `name` 非常有用。

匹配效果的默认行为是在鼠标悬停时激活效果组。可以使用 `behavior` 参数选择其他行为。有关所有可能的行为，请参阅 [Behavior](../HoverEffectGroup/behavior.zh-Hans.md)。

## 更改悬停事件的视图外观

- **hoverEffect(_:)**：将悬停效果应用于此视图。

- **HoverEffect**：指针悬停在视图上时应用的效果。

- **hoverEffect(_:in:isEnabled:)**：为该视图应用悬停效果，并可选择将其添加到 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)。

- **hoverEffect(in:isEnabled:body:)**：为该视图应用由给定闭包描述的悬停效果。

- **CustomHoverEffect**：一种类型，表示当指针悬停在视图上或有人查看视图时，视图应如何变化。

- **ContentHoverEffect**：一个 `CustomHoverEffect`，使用闭包在悬停时为视图应用效果。

- **HoverEffectGroup**：描述一组同时激活的效果。

- **hoverEffectGroup()**：为所有子视图上定义的效果添加一个隐式的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，以便在鼠标悬停于此视图或任何子视图时，添加到子视图的所有效果作为一个组激活。

- **hoverEffectGroup(_:)**：为所有子视图上定义的效果添加一个 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，并在鼠标悬停于此视图或任何子视图时激活该组效果。

- **GroupHoverEffect**：一个 `CustomHoverEffect`，用于激活一个指定的效果组。

- **HoverEffectContent**：一种类型，用于描述视图在特定悬停效果阶段的效果。

- **EmptyHoverEffectContent**：一个空的基础效果，可用于构建其他效果。

- **handPointerBehavior(_:)**：设置用户与视图交互时手形指针的行为。

- **HandPointerBehavior**：可应用于用户与视图交互时手形指针的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/hoverEffectGroup(id:in:behavior:)
crawled: 2025-12-02T17:42:05Z
---

# hoverEffectGroup(id:in:behavior:)

**Instance Method**

Adds a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.

## Declaration

```swift
nonisolated func hoverEffectGroup(id: String? = nil, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup) -> some View

```

## Parameters

- **id**: An optional id to give the group. If provided, the group will be uniquely identified by combining the id and the namespace.
- **namespace**: The namespace that identifies the group. If `nil`, this modifier has no effect.
- **behavior**: How the effect will behave relative to other effects in the group.

## Return Value

A new effect that is matched to other effects in the same group.

## Discussion

You use this modifier when all effects defined on a view and its subviews should activate together. In the following example hovering anywhere over the view will activate the `hoverEffect`s added to the `Text` and the background view, as well as any effects added to the group by other views:

```swift
struct EffectView: View {
    @Namespace var namespace

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
        .hoverEffectGroup(in: namespace)
    }
}
```

The effect group is uniquely identified by combining the `id` and `namespace` parameters. If an `id` is not provided, the effect will be identified by the `namespace` alone. Providing a `name` is useful when creating effects that use multiple, related groups.

The default behavior of a matched effect is to activate the effect group when hovered. The `behavior` parameter can be used to choose alternative behaviors. See [Behavior](../HoverEffectGroup/behavior.zh-Hans.md) for all possible behaviors.

## Changing view appearance for hover events

- **hoverEffect(_:)**: Applies a hover effect to this view.
- **HoverEffect**: An effect applied when the pointer hovers over a view.
- **hoverEffect(_:in:isEnabled:)**: Applies a hover effect to this view, optionally adding it to a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md).
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect to this view described by the given closure.
- **CustomHoverEffect**: A type that represents how a view should change when a pointer hovers over a view, or when someone looks at the view.
- **ContentHoverEffect**: A `CustomHoverEffect` that applies effects to a view on hover using a closure.
- **HoverEffectGroup**: Describes a grouping of effects that activate together.
- **hoverEffectGroup()**: Adds an implicit [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, so that all effects added to subviews activate as a group whenever this view or any descendant views are hovered.
- **hoverEffectGroup(_:)**: Adds a [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to all effects defined on descendant views, and activates the group whenever this view or any descendant views are hovered.
- **GroupHoverEffect**: A `CustomHoverEffect` that activates a named group of effects.
- **HoverEffectContent**: A type that describes the effects of a view for a particular hover effect phase.
- **EmptyHoverEffectContent**: An empty base effect that you use to build other effects.
- **handPointerBehavior(_:)**: Sets the behavior of the hand pointer while the user is interacting with the view.
- **HandPointerBehavior**: A behavior that can be applied to the hand pointer while the user is interacting with a view.

