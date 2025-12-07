--- 来源：https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffect(in:isEnabled:body:)-swift.type.method

抓取时间：2025-12-03T06:45:41Z

---

# hoverEffect(in:isEnabled:body:)

**类型方法**

创建一个悬停效果，该效果使用给定的闭包应用于视图。

## 声明

```swift
static func hoverEffect<C>(in group: HoverEffectGroup? = nil, isEnabled: Bool = true, body: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> C) -> ContentHoverEffect<C> where Self == ContentHoverEffect<C>, C : HoverEffectContent
```

## 参数

- **group**：可选的 [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md)，用于指定要添加此效果的对象。

- **isEnabled**：效果是否启用。如果 `false` 为真，则悬停时效果不会激活。

- **body**：为效果的每个阶段构造一个 `HoverEffectContent` 的闭包。

## 返回值

使用给定的主体闭包将效果应用于视图的新效果。

## 说明

闭包会提供一个空效果，用于组合效果，以及一个描述请求哪个阶段的布尔值。还会提供一个 [GeometryProxy](../GeometryProxy.zh-Hans.md)，允许效果根据视图的几何体而变化。

通常使用 `CustomHoverEffect/hoverEffect(in:isEnabled:body:)` 或 [hoverEffect(in:isEnabled:body:)](../View/hoverEffect_in_isEnabled_body.zh-Hans.md) 修饰符来创建效果。当需要在其他上下文中创建效果时，请使用此方法。

例如，以下代码使用此方法和 [HoverEffect](../HoverEffect.zh-Hans.md) 来创建文字擦除淡入淡出效果：

```swift
HoverEffect(
    .hoverEffect { e, isActive, _ in
        e.opacity(isActive ? 1 : 0)
    }
)
```


---
source: https://developer.apple.com/documentation/SwiftUI/CustomHoverEffect/hoverEffect(in:isEnabled:body:)-swift.type.method
crawled: 2025-12-03T06:45:41Z
---

# hoverEffect(in:isEnabled:body:)

**Type Method**

Creates a hover effect that applies effects to a view using the given closure.

## Declaration

```swift
static func hoverEffect<C>(in group: HoverEffectGroup? = nil, isEnabled: Bool = true, body: @escaping (EmptyHoverEffectContent, Bool, GeometryProxy) -> C) -> ContentHoverEffect<C> where Self == ContentHoverEffect<C>, C : HoverEffectContent
```

## Parameters

- **group**: An optional [HoverEffectGroup](../HoverEffectGroup.zh-Hans.md) to add this effect to.
- **isEnabled**: Whether the effect is enabled or not. If `false`, the effect will not become active when hovered.
- **body**: The closure that constructs a `HoverEffectContent` for each of the effect’s phases.

## Return Value

A new effect that applies effects to a view using the given body closure.

## Discussion

The closure is provided an empty effect that you use to compose effects, as well as a boolean describing which phase is being requested. A [GeometryProxy](../GeometryProxy.zh-Hans.md) is also provided, allowing effects to change based on the view’s geometry.

Typically the `CustomHoverEffect/hoverEffect(in:isEnabled:body:)` or [hoverEffect(in:isEnabled:body:)](../View/hoverEffect_in_isEnabled_body.zh-Hans.md) modifiers are used to create effects. Use this method when you need to create effects in other contexts.

For example, the following code uses this method and [HoverEffect](../HoverEffect.zh-Hans.md) to create a type-erased fade effect:

```swift
HoverEffect(
    .hoverEffect { e, isActive, _ in
        e.opacity(isActive ? 1 : 0)
    }
)
```

