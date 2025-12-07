--- 来源：https://developer.apple.com/documentation/SwiftUI/View/glassEffectUnion(id:namespace:)

抓取时间：2025-11-30T21:08:56Z

---

# glassEffectUnion(id:namespace:)

**实例方法**

将此视图中定义的任何液态玻璃效果关联到具有指定标识符的联合体。

## 声明

```swift
@MainActor @preconcurrency func glassEffectUnion(id: (some Hashable & Sendable)?, namespace: Namespace.ID) -> some View

```

## 说明

您可能希望多个视图的几何形状共同构成一个液态玻璃效果形状。在这种情况下，您可以使用 [glassEffectUnion(id:namespace:)](glassEffectUnion_id_namespace.zh-Hans.md) 来指定某个视图应参与具有特定标识符的液态玻璃效果的联合体。所有具有相同形状和液态玻璃变体的液态玻璃效果将被合并为一个形状。


---
source: https://developer.apple.com/documentation/SwiftUI/View/glassEffectUnion(id:namespace:)
crawled: 2025-11-30T21:08:56Z
---

# glassEffectUnion(id:namespace:)

**Instance Method**

Associates any Liquid Glass effects defined within this view to a union with the provided identifier.

## Declaration

```swift
@MainActor @preconcurrency func glassEffectUnion(id: (some Hashable & Sendable)?, namespace: Namespace.ID) -> some View

```

## Discussion

You may want the geometries of multiple views to contribute to a single Liquid Glass effect shape. In these cases, you can use a [glassEffectUnion(id:namespace:)](glassEffectUnion_id_namespace.zh-Hans.md) to specify that a view should contribute to a union of Liquid Glass effects with a particular identifier. All Liquid Glass effects with the same shape and Liquid Glass variant will be combined into a single shape.

