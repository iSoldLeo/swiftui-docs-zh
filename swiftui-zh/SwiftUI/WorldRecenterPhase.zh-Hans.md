---
来源： https://developer.apple.com/documentation/SwiftUI/WorldRecenterPhase
抓取时间： 2025-12-02T17:20:41Z
---

# 世界中心阶段

**Enumeration**

表示与系统重置事件的某个阶段相关的信息的类型。该类型的值将传递给 View.onWorldRecenter(action:) 中指定的闭包。

### 声明

```swift
enum WorldRecenterPhase
```

## 枚举案例

- **WorldRecenterPhase.began**：应用程序已开始淡出。尚未重新定位。
- **WorldRecenterPhase.ended**：应用程序在重新定位后开始淡入。

## 符合

- 可复制
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/WorldRecenterPhase
crawled: 2025-12-02T17:20:41Z
---

# WorldRecenterPhase

**Enumeration**

A type that represents information associated with a phase of a system recenter event. Values of this type are passed to the closure specified in View.onWorldRecenter(action:).

## Declaration

```swift
enum WorldRecenterPhase
```

## Enumeration Cases

- **WorldRecenterPhase.began**: The app has begun to fade out. It is not re-positioned yet.
- **WorldRecenterPhase.ended**: The app has begun to fade in after it has been re-positioned.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

