--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectGroup(_:)-swift.method

抓取时间：2025-12-01T11:34:45Z

---

# hoverEffectGroup(_:)

**实例方法**

激活此效果，使其成为效果组的一部分。

## 声明

```swift
func hoverEffectGroup(_ group: HoverEffectGroup?) -> some CustomHoverEffect

```

## 参数

- **group**：当鼠标悬停在此视图上时要激活的 `HoverEffectGroup`。如果为 `nil`，则此修饰符无效。

## 返回值

一个新效果，可与同一组中的其他效果一起激活。

## 说明

您可以使用此方法组合影响多个视图的效果。在以下示例中，两个视图的效果位于同一组中。因此，将鼠标悬停在任一视图上都会激活该组中的所有效果，使两个视图都变为完全不透明：

```swift
struct EffectView: View {
    var effectGroup: HoverEffectGroup?

    var body: some View {
        Color.red
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(effectGroup)
            )
        Color.blue
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(effectGroup)
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

## 创建自定义悬停效果

- **hoverEffect(_:in:isEnabled:)**：将此效果与给定的 `effect` 并行应用。

- **hoverEffect(in:isEnabled:body:)**：应用基于当前阶段的悬停效果。

- **hoverEffectGroup(id:in:behavior:)**：将此效果作为效果组的一部分激活。

- **hoverEffectDisabled(_:)**：禁用此悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffectGroup(_:)-swift.method
crawled: 2025-12-01T11:34:45Z
---

# hoverEffectGroup(_:)

**Instance Method**

Activates this effect as part of an effect group.

## Declaration

```swift
func hoverEffectGroup(_ group: HoverEffectGroup?) -> some CustomHoverEffect

```

## Parameters

- **group**: The `HoverEffectGroup` to activate when this view is hovered. If `nil`, this modifier has no effect.

## Return Value

A new effect that activates with other effects in the same group.

## Discussion

You use this method to compose effects that affect multiple views in concert. In the following example, both views’ effects are in the same group. As a result, hovering over either view will activate all effects in the group, causing both views to become fully opaque:

```swift
struct EffectView: View {
    var effectGroup: HoverEffectGroup?

    var body: some View {
        Color.red
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(effectGroup)
            )
        Color.blue
            .frame(width: 100, height: 100)
            .hoverEffect(
                FadeEffect().hoverEffectGroup(effectGroup)
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

## Creating custom hover effects

- **hoverEffect(_:in:isEnabled:)**: Applies this effect in parallel with the given `effect`.
- **hoverEffect(in:isEnabled:body:)**: Applies a hover effect based on the current phase.
- **hoverEffectGroup(id:in:behavior:)**: Activates this effect as part of an effect group.
- **hoverEffectDisabled(_:)**: Disables this hover effect.

