---
来源： https://developer.apple.com/documentation/SwiftUI/FrameResizeDirection
抓取时间： 2025-12-03T06:45:23Z
---

# 缩小框架方向

**Enumeration**

调整矩形框架大小的方向。

## 声明

```swift
@frozen enum FrameResizeDirection
```

## 结构

- **FrameResizeDirection.Set**：一组有效的帧大小调整方向。

## 枚举案例

- **FrameResizeDirection.inward**：表示可以向内调整帧的大小，使其变小。
- **FrameResizeDirection.outward**：表示可以向外调整帧的大小，使其变大。

## 支持类型

- **HorizontalDirection**：水平轴上的一个方向。
- **VerticalDirection**：水平轴上的一个方向。
- **FrameResizePosition**：水平轴上的一个方向：调整矩形框大小时沿矩形框周边（边和角）的位置。

## 符合

- 比特可复制
- CaseIterable
- 可复制
- 等价
- Hashable
- 原始可表示
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/FrameResizeDirection
crawled: 2025-12-03T06:45:23Z
---

# FrameResizeDirection

**Enumeration**

The direction in which a rectangular frame can be resized.

## Declaration

```swift
@frozen enum FrameResizeDirection
```

## Structures

- **FrameResizeDirection.Set**: An efficient set of frame resize directions.

## Enumeration Cases

- **FrameResizeDirection.inward**: Indicates that the frame can be resized inwards to be smaller.
- **FrameResizeDirection.outward**: Indicates that the frame can be resized outwards to be larger.

## Supporting types

- **HorizontalDirection**: A direction on the horizontal axis.
- **VerticalDirection**: A direction on the horizontal axis.
- **FrameResizePosition**: The position along the perimeter of a rectangular frame (its edges and corners) from which it’s resized.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

