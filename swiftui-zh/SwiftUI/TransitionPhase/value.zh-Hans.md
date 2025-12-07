---
来源： https://developer.apple.com/documentation/SwiftUI/TransitionPhase/value
抓取时间： 2025-12-03T06:16:42Z
---

# 值

**实例属性**

一个值，可用于乘以根据不同阶段应用的不同效果。

## 声明

```swift
var value: Double { get }
```

## 返回值

在 `identity` 情况下为 0，在 `willAppear` 情况下为 -1.0，在 `didDisappear` 情况下为 1.0。

## 获取相位特性

- **isIdentity**：布尔值，表示转换是否具有标识效果，即不改变其视图的外观。


---
source: https://developer.apple.com/documentation/SwiftUI/TransitionPhase/value
crawled: 2025-12-03T06:16:42Z
---

# value

**Instance Property**

A value that can be used to multiply effects that are applied differently depending on the phase.

## Declaration

```swift
var value: Double { get }
```

## Return Value

Zero when in the `identity` case, -1.0 for `willAppear`, and 1.0 for `didDisappear`.

## Getting phase characteristics

- **isIdentity**: A Boolean that indicates whether the transition should have an identity effect, i.e. not change the appearance of its view.

