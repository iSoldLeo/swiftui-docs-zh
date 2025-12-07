--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/animation(_:body:)

抓取时间：2025-12-01T11:34:59Z

---

# animation(_:body:)

**实例方法**

将给定的 [Animation](../Animation.zh-Hans.md) 应用于 `body` 闭包内的所有效果。

## 声明

```swift
func animation(_ animation: Animation?, body: (EmptyHoverEffectContent) -> some HoverEffectContent) -> some HoverEffectContent

```

## 参数

- **animation**：用于效果过渡的动画。如果为 `nil`，则效果不会动画。

- **body**：用于指定要动画的效果的代码块。必须使用提供的内容来构建效果，否则行为未定义。

## 返回值

一种结合了 `body` 中定义的效果的新效果

## 说明

`body` 闭包中定义的任何效果都将与此效果结合，并且 `animation` 将用于在应用这些效果时为它们的变化添加动画效果。

在以下示例中，视图在激活效果时将使用 `.easeIn` 动画，而在效果失效时使用 `.easeOut` 动画：

```swift
Color.red
    .hoverEffect { effect, isActive, proxy in
        effect.animation(isActive ? .easeIn : .easeOut) {
            $0.opacity(isActive ? 1 : 0.5)
        }
    }
```


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectContent/animation(_:body:)
crawled: 2025-12-01T11:34:59Z
---

# animation(_:body:)

**Instance Method**

Applies the given [Animation](../Animation.zh-Hans.md) to all effects within the `body` closure.

## Declaration

```swift
func animation(_ animation: Animation?, body: (EmptyHoverEffectContent) -> some HoverEffectContent) -> some HoverEffectContent

```

## Parameters

- **animation**: The animation to use for the effect transition. If `nil` the effects will not animate.
- **body**: A block used to specify the effects to animate. You must use the provided content to build the effects, or behavior is undefined.

## Return Value

A new effect that combines the effects defined in `body` with

## Discussion

Any effects defined within the `body` closure will be combined with this effect, and the `animation` will used to animate those effects’ changes when the effects are applied.

In the following example, the view will use the `.easeIn` animation when activating the effect, but `.easeOut` when the effect becomes inactive:

```swift
Color.red
    .hoverEffect { effect, isActive, proxy in
        effect.animation(isActive ? .easeIn : .easeOut) {
            $0.opacity(isActive ? 1 : 0.5)
        }
    }
```

