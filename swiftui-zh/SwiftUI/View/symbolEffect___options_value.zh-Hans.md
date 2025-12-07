--- 来源：https://developer.apple.com/documentation/SwiftUI/View/symbolEffect(_:options:value:)

抓取时间：2025-11-30T21:20:57Z

---

# symbolEffect(_:options:value:)

**实例方法**

返回一个添加了符号效果的新视图。

## 声明

```swift
nonisolated func symbolEffect<T, U>(_ effect: T, options: SymbolEffectOptions = .default, value: U) -> some View where T : DiscreteSymbolEffect, T : SymbolEffect, U : Equatable

```

## 参数

- **effect**：要添加到视图的符号效果。视图的父视图添加的现有效果将被保留，但可能会被新效果覆盖。添加的效果将应用于子视图包含的视图。

- **value**：要监视更改的值，每次值更改时都会触发动画。

## 返回值

添加符号效果后的视图副本。

## 说明

以下示例为两个符号图像添加弹跳效果，动画会在每次 `counter` 更改时播放：

```swift
VStack {
    Image(systemName: "bolt.slash.fill")
    Image(systemName: "folder.fill.badge.person.crop")
}
.symbolEffect(.bounce, value: counter)
```

## 管理符号效果

- **symbolEffect(_:options:isActive:)**：返回一个添加了符号效果的新视图。

- **symbolEffectsRemoved(_:)**：返回一个新视图，其继承的符号图像效果可能被移除或保持不变。

- **SymbolEffectTransition**：创建一个过渡效果，将“出现”、“消失”、“绘制”或“绘制结束”符号动画应用于插入或移除的视图层级结构中的符号图像。


---
source: https://developer.apple.com/documentation/SwiftUI/View/symbolEffect(_:options:value:)
crawled: 2025-11-30T21:20:57Z
---

# symbolEffect(_:options:value:)

**Instance Method**

Returns a new view with a symbol effect added to it.

## Declaration

```swift
nonisolated func symbolEffect<T, U>(_ effect: T, options: SymbolEffectOptions = .default, value: U) -> some View where T : DiscreteSymbolEffect, T : SymbolEffect, U : Equatable

```

## Parameters

- **effect**: A symbol effect to add to the view. Existing effects added by ancestors of the view are preserved, but may be overridden by the new effect. Added effects will be applied to the ``SwiftUI/Image` views contained by the child view.
- **value**: The value to monitor for changes, the animation is triggered each time the value changes.

## Return Value

A copy of the view with a symbol effect added.

## Discussion

The following example adds a bounce effect to two symbol images, the animation will play each time `counter` changes:

```swift
VStack {
    Image(systemName: "bolt.slash.fill")
    Image(systemName: "folder.fill.badge.person.crop")
}
.symbolEffect(.bounce, value: counter)
```

## Managing symbol effects

- **symbolEffect(_:options:isActive:)**: Returns a new view with a symbol effect added to it.
- **symbolEffectsRemoved(_:)**: Returns a new view with its inherited symbol image effects either removed or left unchanged.
- **SymbolEffectTransition**: Creates a transition that applies the Appear, Disappear, DrawOn or DrawOff symbol animation to symbol images within the inserted or removed view hierarchy.

