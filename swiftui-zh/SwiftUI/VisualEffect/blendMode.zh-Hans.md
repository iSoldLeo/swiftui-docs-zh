---
来源： https://developer.apple.com/documentation/SwiftUI/VisualEffect/blendMode(_:)
抓取时间： 2025-12-01T11:19:12Z
---

# blendMode(_:)

**实例方法**

设置该视图与重叠视图合成时的混合模式。

## 声明

```swift
func blendMode(_ blendMode: BlendMode) -> some VisualEffect

```

## 参数

- **blendMode**：用于合成的[BlendMode](../BlendMode.zh-Hans.md)。

## 返回值

对该视图应用`blendMode` 的效果。

## 讨论

使用`blendMode(_:)` 可以合并重叠的视图，并使用不同的视觉效果产生效果。[BlendMode](../BlendMode.zh-Hans.md)枚举定义了许多可能的效果。


---
source: https://developer.apple.com/documentation/SwiftUI/VisualEffect/blendMode(_:)
crawled: 2025-12-01T11:19:12Z
---

# blendMode(_:)

**Instance Method**

Sets the blend mode for compositing this view with overlapping views.

## Declaration

```swift
func blendMode(_ blendMode: BlendMode) -> some VisualEffect

```

## Parameters

- **blendMode**: The [BlendMode](../BlendMode.zh-Hans.md) for compositing.

## Return Value

An effect that applies `blendMode` to this view.

## Discussion

Use `blendMode(_:)` to combine overlapping views and use a different visual effect to produce the result. The [BlendMode](../BlendMode.zh-Hans.md) enumeration defines many possible effects.

