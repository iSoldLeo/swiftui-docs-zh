--- 来源：https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup/Behavior/preservesGroup

抓取时间：2025-12-04T13:38:30Z

---

# preservesGroup

**类型属性**

保持组的当前阶段。

## 声明

```swift
static let preservesGroup: HoverEffectGroup.Behavior
```

## 讨论

当某个效果不应激活组内的其他效果时，除非该组已处于活动状态，否则可以使用此行为。这有助于描述视图的哪些部分应触发效果，同时允许其他区域简单地阻止效果结束。


---
source: https://developer.apple.com/documentation/SwiftUI/HoverEffectGroup/Behavior/preservesGroup
crawled: 2025-12-04T13:38:30Z
---

# preservesGroup

**Type Property**

Preserves the current phase of the group.

## Declaration

```swift
static let preservesGroup: HoverEffectGroup.Behavior
```

## Discussion

Use this behavior when an effect should not activate other effects in a group, unless the group already active. This is useful for describing which parts of a view should trigger an effect, while allowing other areas to simply prevent the effect from ending.

