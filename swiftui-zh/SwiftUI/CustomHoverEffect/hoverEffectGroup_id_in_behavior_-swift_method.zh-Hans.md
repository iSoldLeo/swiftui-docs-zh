--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectGroup(id:in:behavior:)-swift.method

抓取时间：2025-12-01T11:34:45Z

---

# hoverEffectGroup(id:in:behavior:)

**实例方法**

激活此效果作为效果组的一部分。

## 声明

```swift
func hoverEffectGroup(id: String? = nil, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup) -> some CustomHoverEffect

```

## 参数

- **id**：用于为效果组指定的可选 ID。如果提供，则该效果组将通过组合 ID 和命名空间来唯一标识。

- **namespace**：用于标识效果组的命名空间。如果为 `nil`，则此修饰符无效。

- **behavior**：该效果相对于组内其他效果的行为方式。

## 返回值

一个与同一组中其他效果同时激活的新效果。

## 说明

您可以使用此方法组合多个效果，使它们同时改变多个视图。在以下示例中，两个视图的效果都在同一组中。因此，将鼠标悬停在任一视图上都会激活该组中的所有效果，使两个视图都变为完全不透明：

```swift
struct EffectView: View {
    @Namespace var namespace

    var body: some View {
        Color.red
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(in: namespace)
            )
        Color.blue
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(in: namespace)
            )
    }
}

struct FadeEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, _ in
            effect.opacity(isActive ? 1 : 0.5)
        }
    }
}
```

效果组由 `id` 和 `namespace` 参数组合而成，用于唯一标识。如果未提供 `id`，则效果将仅由 `namespace` 标识。当创建使用多个密切相关组的效果时，提供 `id` 非常有用。

效果的默认行为是在鼠标悬停时激活效果组。可以使用 `behavior` 参数选择其他行为。有关所有可能的行为，请参阅 [Behavior](../HoverEffectGroup/behavior.zh-Hans.md)。

## 创建自定义悬停效果

- **hoverEffect(_:in:isEnabled:)**：将此效果与给定的 `effect` 并行应用。

- **hoverEffect(in:isEnabled:body:)**：应用基于当前阶段的悬停效果。

- **hoverEffectGroup(_:)**：将此效果作为效果组的一部分激活。

- **hoverEffectDisabled(_:)**：禁用此悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectGroup(id:in:behavior:)-swift.method
crawled: 2025-12-01T11:34:45Z
---

# hoverEffectGroup(id:in:behavior:)

**Instance Method**

Activates this effect as part of an effect group.

## Declaration

```swift
func hoverEffectGroup(id: String? = nil, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup) -> some CustomHoverEffect

```

## Parameters

- **id**: An optional id to give the group. If provided, the group will be uniquely identified by combining the id and the namespace.
- **namespace**: The namespace that identifies the group. If `nil`, this modifier has no effect.
- **behavior**: How the effect will behave relative to other effects in the group.

## Return Value

A new effect that activates with other effects in the same group.

## Discussion

You use this method to compose effects that change multiple views in concert. In the following example, both views’ effects are in the same group. As a result, hovering over either view will activate all effects in the group, causing both views to become fully opaque:

```swift
struct EffectView: View {
    @Namespace var namespace

    var body: some View {
        Color.red
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(in: namespace)
            )
        Color.blue
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(in: namespace)
            )
    }
}

struct FadeEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, _ in
            effect.opacity(isActive ? 1 : 0.5)
        }
    }
}
```

The effect group is uniquely identified by combining the `id` and `namespace` parameters. If an `id` is not provided, the effect will be identified by the `namespace` alone. Providing an `id` is useful when creating effects that use multiple, closely-related groups.

The default behavior of an effect is to activate the effect group when hovered. The `behavior` parameter can be used to choose alternative behaviors. See [Behavior](../HoverEffectGroup/behavior.zh-Hans.md) for all possible behaviors.

## Creating custom hover effects

- **hoverEffect(_:in:isEnabled:)**: Applies this effect in parallel with the given `effect`.
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect based on the current phase.
- **hoverEffectGroup(_:)**: Activates this effect as part of an effect group.
- **hoverEffectDisabled(_:)**: Disables this hover effect.

