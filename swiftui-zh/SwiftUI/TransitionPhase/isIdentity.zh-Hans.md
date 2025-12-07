---
来源： https://developer.apple.com/documentation/SwiftUI/TransitionPhase/isIdentity
抓取时间： 2025-12-03T06:16:42Z
---

# isIdentity

**实例属性**

布尔值，用于指示转换是否具有身份效果，即不改变视图的外观。

### 声明

```swift
var isIdentity: Bool { get }
```

## 讨论

这在`identity`阶段是正确的。

## 获取相位特征

- **value**：一个值，可以用来乘以根据相位不同而应用不同的效果。


---
source: https://developer.apple.com/documentation/SwiftUI/TransitionPhase/isIdentity
crawled: 2025-12-03T06:16:42Z
---

# isIdentity

**Instance Property**

A Boolean that indicates whether the transition should have an identity effect, i.e. not change the appearance of its view.

## Declaration

```swift
var isIdentity: Bool { get }
```

## Discussion

This is true in the `identity` phase.

## Getting phase characteristics

- **value**: A value that can be used to multiply effects that are applied differently depending on the phase.

