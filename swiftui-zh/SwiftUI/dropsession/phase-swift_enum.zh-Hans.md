---
来源： https://developer.apple.com/documentation/swiftui/dropsession/phase-swift.enum
抓取时间： 2025-12-03T06:47:06Z
---

# DropSession.Phase

**Enumeration**

当前丢弃会话的阶段。

## 声明

```swift
enum Phase
```

## 枚举案例

- **DropSession.Phase.active**：空投会话在空投目的地内处于活动状态。
- **DropSession.Phase.dataTransferCompleted**：已传送拖放的项目。您可以删除临时项目，必要时执行任何清理。
- **DropSession.Phase.ended(_:)**：空投已结束。
- **DropSession.Phase.entering**：空投会话正在进入空投目的地。
- **DropSession.Phase.exiting**：空投会话已退出空投目的地。

## 符合

- 可复制
- 自定义字符串可转换
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/dropsession/phase-swift.enum
crawled: 2025-12-03T06:47:06Z
---

# DropSession.Phase

**Enumeration**

The phase of the current drop session.

## Declaration

```swift
enum Phase
```

## Enumeration Cases

- **DropSession.Phase.active**: The drop session is active inside the drop destination.
- **DropSession.Phase.dataTransferCompleted**: Dragged items have been transferred. You can remove temporary items, perform any cleanup if needed.
- **DropSession.Phase.ended(_:)**: The drop has ended.
- **DropSession.Phase.entering**: The drop session is entering the drop destination.
- **DropSession.Phase.exiting**: The drop session has exited the drop destination.

## Conforms To

- Copyable
- CustomStringConvertible
- Equatable
- Hashable
- Sendable
- SendableMetatype

