--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectGroup(id:in:behavior:)-swift.type.method

抓取时间：2025-12-01T11:34:54Z

---

# hoverEffectGroup(id:in:behavior:)

**类型方法**

创建一个效果，该效果会激活一个指定名称的效果组。

## 声明

```swift
static func hoverEffectGroup(id: String? = nil, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup) -> GroupHoverEffect
```

## 参数

- **id**：用于为效果组指定一个可选的 ID。如果提供此 ID，则该效果组将通过组合 ID 和命名空间来唯一标识。

- **namespace**：用于标识效果组的命名空间。如果为 `nil`，则此修饰符无效。

- **behavior**：该效果相对于组内其他效果的行为方式。

## 返回值

激活指定效果组的新效果。

## 说明

效果组由 `id` 和 `namespace` 参数组合而成，用于唯一标识。如果未提供 `id` 参数，则效果将仅由 `namespace` 参数标识。当创建使用多个密切相关组的效果时，提供 `id` 参数非常有用。

效果的默认行为是在鼠标悬停时激活效果组。可以使用 `behavior` 参数选择其他行为。有关所有可能的行为，请参阅 [Behavior](../HoverEffectGroup/behavior.zh-Hans.md) 参数。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectGroup(id:in:behavior:)-swift.type.method
crawled: 2025-12-01T11:34:54Z
---

# hoverEffectGroup(id:in:behavior:)

**Type Method**

Creates an effect that activates a named group of effects.

## Declaration

```swift
static func hoverEffectGroup(id: String? = nil, in namespace: Namespace.ID, behavior: HoverEffectGroup.Behavior = .activatesGroup) -> GroupHoverEffect
```

## Parameters

- **id**: An optional id to give the group. If provided, the group will be uniquely identified by combining the id and the namespace.
- **namespace**: The namespace that identifies the group. If `nil`, this modifier has no effect.
- **behavior**: How the effect will behave relative to other effects in the group.

## Return Value

A new effect that activates the given effect group.

## Discussion

The effect group is uniquely identified by combining the `id` and `namespace` parameters. If an `id` is not provided, the effect will be identified by the `namespace` alone. Providing an `id` is useful when creating effects that use multiple, closely-related groups.

The default behavior of an effect is to activate the effect group when hovered. The `behavior` parameter can be used to choose alternative behaviors. See [Behavior](../HoverEffectGroup/behavior.zh-Hans.md) for all possible behaviors.

