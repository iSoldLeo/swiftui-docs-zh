--- 来源：https://developer.apple.com/documentation/SwiftUI/Chirality
抓取时间：2025-12-02T17:40:57Z

---

# 手性

**Enumeration**

手势的手性，或称惯用手。

## 声明

```swift
@frozen enum Chirality
```

## 枚举情况

- **Chirality.left**：表示左手手势。

- **Chirality.right**：表示右手手势。

## 识别空间事件

- **SpatialEventGesture**：提供有关正在进行的空间事件（例如点击和触摸）信息的手势。

- **SpatialEventCollection**：指向特定视图的空间输入事件集合。

## 符合以下规范

- 位可复制 (BitwiseCopyable)

- 可复制 (Copyable)

- 可等值 (Equatable)

- 可哈希 (Hashable)

- 可发送 (Sendable)

- 可发送元数据类型 (SendableMetatype)


---
source: https://developer.apple.com/documentation/SwiftUI/Chirality
crawled: 2025-12-02T17:40:57Z
---

# Chirality

**Enumeration**

The chirality, or handedness, of a pose.

## Declaration

```swift
@frozen enum Chirality
```

## Enumeration Cases

- **Chirality.left**: Indicates a left-handed pose.
- **Chirality.right**: Indicates a right-handed pose.

## Recognizing spatial events

- **SpatialEventGesture**: A gesture that provides information about ongoing spatial events like clicks and touches.
- **SpatialEventCollection**: A collection of spatial input events that target a specific view.

## Conforms To

- BitwiseCopyable
- Copyable
- Equatable
- Hashable
- Sendable
- SendableMetatype

