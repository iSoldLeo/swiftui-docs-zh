---
来源： https://developer.apple.com/documentation/SwiftUI/FrameResizePosition
抓取时间： 2025-12-03T06:45:22Z
---

# 框架调整位置

**Enumeration**

调整矩形边框大小时沿边框周长（边和角）的位置。

## 声明

```swift
@frozen enum FrameResizePosition
```

## 枚举案例

- **FrameResizePosition.bottom**：边框的底边。
- **FrameResizePosition.bottomLeading**：边框的底部前角。
- **FrameResizePosition.bottomTrailing**：边框的底边：边框的尾部底角。
- **FrameResizePosition.leading**：边框的前缘。
- **FrameResizePosition.top**：边框的上边缘：边框的上边缘。
- **FrameResizePosition.topLeading**：边框的前角。
- **FrameResizePosition.topTrailing**：边框的顶部后缘。
- **FrameResizePosition.trailing**：机架后缘。

## 支持类型

- **HorizontalDirection**：水平轴上的一个方向。
- **VerticalDirection**：水平轴上的一个方向。
- **FrameResizeDirection**：水平轴上的一个方向：可调整矩形框大小的方向。

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
source: https://developer.apple.com/documentation/SwiftUI/FrameResizePosition
crawled: 2025-12-03T06:45:22Z
---

# FrameResizePosition

**Enumeration**

The position along the perimeter of a rectangular frame (its edges and corners) from which it’s resized.

## Declaration

```swift
@frozen enum FrameResizePosition
```

## Enumeration Cases

- **FrameResizePosition.bottom**: The bottom edge of the frame.
- **FrameResizePosition.bottomLeading**: The bottom leading corner of the frame.
- **FrameResizePosition.bottomTrailing**: The bottom trailing corner of the frame.
- **FrameResizePosition.leading**: The leading edge of the frame.
- **FrameResizePosition.top**: The top edge of the frame.
- **FrameResizePosition.topLeading**: The top leading corner of the frame.
- **FrameResizePosition.topTrailing**: The top trailing edge of the frame.
- **FrameResizePosition.trailing**: The trailing edge of the frame.

## Supporting types

- **HorizontalDirection**: A direction on the horizontal axis.
- **VerticalDirection**: A direction on the horizontal axis.
- **FrameResizeDirection**: The direction in which a rectangular frame can be resized.

## Conforms To

- BitwiseCopyable
- CaseIterable
- Copyable
- Equatable
- Hashable
- RawRepresentable
- Sendable
- SendableMetatype

