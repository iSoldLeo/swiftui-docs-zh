--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffect(in:isEnabled:body:)-swift.method

抓取时间：2025-12-03T06:45:33Z
---

# hoverEffect(in:isEnabled:body:)

**实例方法**

根据当前阶段应用悬停效果。

## 声明

```swift
func hoverEffect(in group: HoverEffectGroup? = nil, isEnabled: Bool = true, body: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> some HoverEffectContent) -> some CustomHoverEffect

```

## 参数

- **group**：可选的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，用于添加此效果。

- **isEnabled**：效果是否启用。如果 `false`，则应用效果的非激活状态，悬停时不会应用激活状态。

- **body**：为效果的每个阶段构造一个 `HoverEffectContent` 的闭包。

## 返回值

一种新的效果，当鼠标悬停在视图上时，视图的外观会发生改变。

## 说明

您可以使用此修改器来描述鼠标悬停在视图上时应该如何改变视图。给定的闭包会提供一个空的效果，您可以使用该效果来组合效果，以及一个布尔值，用于描述请求的是哪个阶段。此外，还会提供一个 [GeometryProxy](../GeometryProxy.zh-Hans.md)，允许效果根据视图的几何形状进行改变。

在以下示例中，该效果会在视图处于非活动状态时将其缩放比例设置为 1.0，然后在激活时缩放比例设置为 1.1：

```swift
struct ScaleHoverEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, proxy in
            effect.scaleEffect(!isActive ? 1.0 : 1.1)
        }
    }
}
```

使用 [animation(_:body:)](../HoverEffectContent/animation___body.zh-Hans.md) 修改器来指定视觉变化的动画方式。

## 创建自定义悬停效果

- **hoverEffect(_:in:isEnabled:)**：将此效果与指定的 `effect` 并行应用。

- **hoverEffectGroup(_:)**：将此效果作为效果组的一部分激活。

- **hoverEffectGroup(id:in:behavior:)**：将此效果作为效果组的一部分激活。

- **hoverEffectDisabled(_:)**：禁用此悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffect(in:isEnabled:body:)-swift.method
crawled: 2025-12-03T06:45:33Z
---

# hoverEffect(in:isEnabled:body:)

**Instance Method**

Applies a hover effect based on the current phase.

## Declaration

```swift
func hoverEffect(in group: HoverEffectGroup? = nil, isEnabled: Bool = true, body: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> some HoverEffectContent) -> some CustomHoverEffect

```

## Parameters

- **group**: An optional [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to add this effect to.
- **isEnabled**: Whether the effect is enabled or not. If `false`, the effect’s inactive state will be applied, and it will not apply the active state when hovered.
- **body**: The closure that constructs a `HoverEffectContent` for each of the effect’s phases.

## Return Value

A new effect that changes a view’s appearance when hovered.

## Discussion

You use this modifier to describe how a view should change when hovered. The given closure is provided an empty effect that you use to compose an effect, as well as a boolean describing which phase is being requested. A [GeometryProxy](../GeometryProxy.zh-Hans.md) is also provided, allowing effects to change based on the view’s geometry.

In the following example, the effect will apply a scale of 1.0 to a view when inactive, and then scale to 1.1 when active:

```swift
struct ScaleHoverEffect: CustomHoverEffect {
    func body(content: Content) -> some CustomHoverEffect {
        content.hoverEffect { effect, isActive, proxy in
            effect.scaleEffect(!isActive ? 1.0 : 1.1)
        }
    }
}
```

Use the [animation(_:body:)](../HoverEffectContent/animation___body.zh-Hans.md) modifier to specify how visual changes should be animated.

## Creating custom hover effects

- **hoverEffect(_:in:isEnabled:)**: Applies this effect in parallel with the given `effect`.
- **hoverEffectGroup(_:)**: Activates this effect as part of an effect group.
- **hoverEffectGroup(id:in:behavior:)**: Activates this effect as part of an effect group.
- **hoverEffectDisabled(_:)**: Disables this hover effect.

