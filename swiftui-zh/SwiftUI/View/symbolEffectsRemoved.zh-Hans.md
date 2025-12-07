--- 来源：https://developer.apple.com/documentation/SwiftUI/View/symbolEffectsRemoved(_:)

抓取时间：2025-11-30T21:20:58Z

---

# symbolEffectsRemoved(_:)

**实例方法**

返回一个新视图，该视图已移除或保留其继承的符号图像效果。

## 声明

```swift
nonisolated func symbolEffectsRemoved(_ isEnabled: Bool = true) -> some View

```

## 参数

- **isEnabled**：是否移除继承的符号效果。

## 返回值

移除或保留符号效果的视图副本。

## 讨论

以下示例为两个符号图像添加重复脉冲效果，然后禁用其中一个图像的效果：

```swift
VStack {
    Image(systemName: "bolt.slash.fill") // does not pulse
        .symbolEffectsRemoved()
    Image(systemName: "folder.fill.badge.person.crop") // pulses
}
.symbolEffect(.pulse)
```

## 管理符号效果

- **symbolEffect(_:options:isActive:)**：返回一个添加了符号效果的新视图。

- **symbolEffect(_:options:value:)**：返回一个添加了符号效果的新视图。

- **SymbolEffectTransition**：创建一个过渡效果，将“出现”、“消失”、“绘制”或“绘制结束”符号动画应用于插入或移除的视图层级结构中的符号图像。


---
source: https://developer.apple.com/documentation/SwiftUI/View/symbolEffectsRemoved(_:)
crawled: 2025-11-30T21:20:58Z
---

# symbolEffectsRemoved(_:)

**Instance Method**

Returns a new view with its inherited symbol image effects either removed or left unchanged.

## Declaration

```swift
nonisolated func symbolEffectsRemoved(_ isEnabled: Bool = true) -> some View

```

## Parameters

- **isEnabled**: Whether to remove inherited symbol effects or not.

## Return Value

A copy of the view with its symbol effects either removed or left unchanged.

## Discussion

The following example adds a repeating pulse effect to two symbol images, but then disables the effect on one of them:

```swift
VStack {
    Image(systemName: "bolt.slash.fill") // does not pulse
        .symbolEffectsRemoved()
    Image(systemName: "folder.fill.badge.person.crop") // pulses
}
.symbolEffect(.pulse)
```

## Managing symbol effects

- **symbolEffect(_:options:isActive:)**: Returns a new view with a symbol effect added to it.
- **symbolEffect(_:options:value:)**: Returns a new view with a symbol effect added to it.
- **SymbolEffectTransition**: Creates a transition that applies the Appear, Disappear, DrawOn or DrawOff symbol animation to symbol images within the inserted or removed view hierarchy.

