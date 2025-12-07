---
来源： https://developer.apple.com/documentation/swiftui/scrolltransitionphase/value
抓取时间： 2025-12-04T13:37:23Z
---

# 值

**实例属性**

相位衍生值，可用于缩放或修改效果。

## 声明

```swift
var value: Double { get }
```

## 讨论

在 topLeading 阶段返回 -1.0，在 identity 阶段返回 0，在 bottomTrailing 阶段返回 1.0。

## 访问阶段状态

- **isIdentity**


---
source: https://developer.apple.com/documentation/swiftui/scrolltransitionphase/value
crawled: 2025-12-04T13:37:23Z
---

# value

**Instance Property**

A phase-derived value that can be used to scale or otherwise modify effects.

## Declaration

```swift
var value: Double { get }
```

## Discussion

Returns -1.0 when in the topLeading phase, zero when in the identity phase, and 1.0 when in the bottomTrailing phase.

## Accessing the phase state

- **isIdentity**

