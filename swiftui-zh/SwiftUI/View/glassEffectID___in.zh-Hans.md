--- 来源：https://developer.apple.com/documentation/SwiftUI/View/glassEffectID(_:in:)

抓取时间：2025-12-02T17:23:51Z

---

# glassEffectID(_:in:)

**实例方法**

为该视图中定义的 Liquid Glass 效果关联一个标识值。

## 声明

```swift
nonisolated func glassEffectID(_ id: (some Hashable & Sendable)?, in namespace: Namespace.ID) -> some View

```

## 说明

您可以将此修饰符与 [glassEffect(_:in:)](glassEffect___in.zh-Hans.md) 视图修饰符和 [GlassEffectContainer](../GlassEffectContainer.zh-Hans.md) 视图一起使用。当两者一起使用时，SwiftUI 会使用此标识符在过渡期间实现形状之间的动画效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/glassEffectID(_:in:)
crawled: 2025-12-02T17:23:51Z
---

# glassEffectID(_:in:)

**Instance Method**

Associates an identity value to Liquid Glass effects defined within this view.

## Declaration

```swift
nonisolated func glassEffectID(_ id: (some Hashable & Sendable)?, in namespace: Namespace.ID) -> some View

```

## Discussion

You use this modifier with the [glassEffect(_:in:)](glassEffect___in.zh-Hans.md) view modifier and a [GlassEffectContainer](../GlassEffectContainer.zh-Hans.md) view. When used together, SwiftUI uses the identifier to animate shapes to and from each other during transitions.

