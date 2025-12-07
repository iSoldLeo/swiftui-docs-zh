--- 来源：https://developer.apple.com/documentation/SwiftUI/SequenceGesture/Value
抓取时间：2025-12-03T06:43:57Z

---

# SequenceGesture.Value

**Enumeration**

序列手势的值，用于检测第一个手势是否成功，以便启动第二个手势。

## 声明

```swift
@frozen enum Value
```

## 获取手势值

- **SequenceGesture.Value.first(_:)**：第一个手势尚未结束。

- **SequenceGesture.Value.second(_:_:)**：第一个手势已结束。

## 符合以下规范

- Copyable

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/SequenceGesture/Value
crawled: 2025-12-03T06:43:57Z
---

# SequenceGesture.Value

**Enumeration**

The value of a sequence gesture that helps to detect whether the first gesture succeeded, so the second gesture can start.

## Declaration

```swift
@frozen enum Value
```

## Getting gesture values

- **SequenceGesture.Value.first(_:)**: The first gesture hasn’t ended.
- **SequenceGesture.Value.second(_:_:)**: The first gesture has ended.

## Conforms To

- Copyable
- Equatable
- Sendable
- SendableMetatype

