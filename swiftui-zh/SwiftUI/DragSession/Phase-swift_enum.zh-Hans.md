---
来源： https://developer.apple.com/documentation/SwiftUI/DragSession/Phase-swift.enum
抓取时间： 2025-12-03T06:46:59Z
---

# DragSession.Phase

**Enumeration**

当前拖动会话的阶段

## 声明

```swift
enum Phase
```

## 枚举案例

- **DragSession.Phase.active**：拖动已移至新位置。
- **DragSession.Phase.dataTransferCompleted**：拖动的项目已转移。您可以删除临时项目，必要时执行任何清理。
- **DragSession.Phase.ended(_:)**：拖动已结束。
- **DragSession.Phase.ending(_:)**：拖动即将结束。
- **DragSession.Phase.initial**：拖动环节即将开始

## 符合

- 可复制
- 自定义字符串可转换
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/DragSession/Phase-swift.enum
crawled: 2025-12-03T06:46:59Z
---

# DragSession.Phase

**Enumeration**

The phase of the current drag session

## Declaration

```swift
enum Phase
```

## Enumeration Cases

- **DragSession.Phase.active**: The drag has moved to a new location.
- **DragSession.Phase.dataTransferCompleted**: Dragged items have been transferred. You can remove temporary items, perform any cleanup if needed.
- **DragSession.Phase.ended(_:)**: The drag has ended.
- **DragSession.Phase.ending(_:)**: The drag is about to finish.
- **DragSession.Phase.initial**: The drag session is about to begin

## Conforms To

- Copyable
- CustomStringConvertible
- Equatable
- Hashable
- Sendable
- SendableMetatype

