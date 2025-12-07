--- 来源：https://developer.apple.com/documentation/swiftui/keypress/result
抓取时间：2025-12-03T06:44:32Z

---

# KeyPress.Result

**Enumeration**

按键事件返回的结果值，指示该事件是否被事件处理。

## 声明

```swift
enum Result
```

## 获取结果

- **KeyPress.Result.handled**：事件被处理，导致分发无法继续。

- **KeyPress.Result.ignored**：事件被忽略，允许分发继续。

## 符合以下规范

- Copyable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/keypress/result
crawled: 2025-12-03T06:44:32Z
---

# KeyPress.Result

**Enumeration**

A result value returned from a key-press action that indicates whether the action consumed the event.

## Declaration

```swift
enum Result
```

## Getting the result

- **KeyPress.Result.handled**: The action consumed the event, preventing dispatch from continuing.
- **KeyPress.Result.ignored**: The action ignored the event, allowing dispatch to continue.

## Conforms To

- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

