--- 来源：https://developer.apple.com/documentation/SwiftUI/GlassEffectTransition/matchedGeometry
抓取时间：2025-12-03T06:08:49Z

---

# matchedGeometry

**类型属性**

返回匹配几何体的玻璃效果过渡。

## 声明

```swift
static var matchedGeometry: GlassEffectTransition { get }
```

## 讨论

匹配几何体过渡允许在过渡的出现或消失阶段，玻璃形状的几何体源自玻璃容器内相邻形状的几何体。

例如，如果新出现的形状位于任何现有形状的间距内，它将使用该形状的几何体进行过渡。

使用 [default](../Animation/default.zh-Hans.md) 时，如果形状的标识不变但其内容发生变化，此过渡将对内容应用额外的缩放和偏移效果。如需禁用这些额外的动画，请提供特定的动画名称，例如 [spring](../Animation/spring.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/GlassEffectTransition/matchedGeometry
crawled: 2025-12-03T06:08:49Z
---

# matchedGeometry

**Type Property**

Returns the matched geometry glass effect transition.

## Declaration

```swift
static var matchedGeometry: GlassEffectTransition { get }
```

## Discussion

The matched geometry transition allows the geometries of glass shapes during an appearance or disappearance phase of a transition to be derived from the geometry of a nearby shape within the glass container.

For example, if a newly appearing shape is within the spacing of any existing shape, it will use that shapes geometry to transition out of.

When using the [default](../Animation/default.zh-Hans.md), this transition applies additional scale and offset effects to content when the identity of the shape does not change but its content does. Opt out of these additional animations by providing a specific animation like [spring](../Animation/spring.zh-Hans.md).

