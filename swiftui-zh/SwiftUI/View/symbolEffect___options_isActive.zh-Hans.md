--- 来源：https://developer.apple.com/documentation/SwiftUI/View/symbolEffect(_:options:isActive:)

抓取时间：2025-12-02T17:35:52Z

---

# symbolEffect(_:options:isActive:)

**实例方法**

返回一个添加了符号效果的新视图。

## 声明

```swift
nonisolated func symbolEffect<T>(_ effect: T, options: SymbolEffectOptions = .default, isActive: Bool = true) -> some View where T : IndefiniteSymbolEffect, T : SymbolEffect

```

## 参数

- **effect**：要添加到视图的符号效果。视图的祖先视图添加的现有效果将被保留，但可能会被新效果覆盖。添加的效果将应用于子视图包含的视图。

- **isActive**：效果是激活还是禁用。

## 返回值

添加符号效果后的视图副本。

## 说明

以下示例为两个符号图像添加重复脉冲效果：

```swift
VStack {
    Image(systemName: "bolt.slash.fill")
    Image(systemName: "folder.fill.badge.person.crop")
}
.symbolEffect(.pulse)
```

## 管理符号效果

- **symbolEffect(_:options:value:)**：返回一个添加了符号效果的新视图。

- **symbolEffectsRemoved(_:)**：返回一个新视图，其继承的符号图像效果可能被移除或保持不变。

- **SymbolEffectTransition**：创建一个过渡效果，将“出现”、“消失”、“绘制”或“绘制结束”符号动画应用于插入或移除的视图层级结构中的符号图像。


---
source: https://developer.apple.com/documentation/SwiftUI/View/symbolEffect(_:options:isActive:)
crawled: 2025-12-02T17:35:52Z
---

# symbolEffect(_:options:isActive:)

**Instance Method**

Returns a new view with a symbol effect added to it.

## Declaration

```swift
nonisolated func symbolEffect<T>(_ effect: T, options: SymbolEffectOptions = .default, isActive: Bool = true) -> some View where T : IndefiniteSymbolEffect, T : SymbolEffect

```

## Parameters

- **effect**: A symbol effect to add to the view. Existing effects added by ancestors of the view are preserved, but may be overridden by the new effect. Added effects will be applied to the ``SwiftUI/Image` views contained by the child view.
- **isActive**: Whether the effect is active or inactive.

## Return Value

A copy of the view with a symbol effect added.

## Discussion

The following example adds a repeating pulse effect to two symbol images:

```swift
VStack {
    Image(systemName: "bolt.slash.fill")
    Image(systemName: "folder.fill.badge.person.crop")
}
.symbolEffect(.pulse)
```

## Managing symbol effects

- **symbolEffect(_:options:value:)**: Returns a new view with a symbol effect added to it.
- **symbolEffectsRemoved(_:)**: Returns a new view with its inherited symbol image effects either removed or left unchanged.
- **SymbolEffectTransition**: Creates a transition that applies the Appear, Disappear, DrawOn or DrawOff symbol animation to symbol images within the inserted or removed view hierarchy.

