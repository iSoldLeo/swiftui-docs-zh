---
来源： https://developer.apple.com/documentation/SwiftUI/DragDropPreviewsFormation
抓取时间： 2025-12-02T17:42:55Z
---

# DragDropPreviewsFormation

**Structure**

在 macOS 上，描述拖动预览的视觉构成方式。拖动源和拖放目标都可以指定所需的预览形式。

## 声明

```swift
struct DragDropPreviewsFormation
```

## 类型属性

- **default**：系统决定的成分。
- **list**：拖动图像垂直布局，不重叠，左边缘对齐。
- **none**：拖动图像保持其设定的相对位置。
- **pile**：拖动图像以随机旋转的方式放置在彼此之上。
- **stack**：拖动图像以对角线方式重叠排列。

## 符合

- 可复制
- 自定义字符串可转换
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/DragDropPreviewsFormation
crawled: 2025-12-02T17:42:55Z
---

# DragDropPreviewsFormation

**Structure**

On macOS, describes the way the dragged previews are visually composed. Both drag sources and drop destination can specify their desired preview formation.

## Declaration

```swift
struct DragDropPreviewsFormation
```

## Type Properties

- **default**: System-determined composition.
- **list**: Drag images are laid out vertically, non-overlapping, and the left edges are aligned.
- **none**: Drag images maintain their set positions relative to each other.
- **pile**: Drag images are placed on top of each other with random rotations.
- **stack**: Drag images are laid out overlapping diagonally.

## Conforms To

- Copyable
- CustomStringConvertible
- Equatable
- Hashable
- Sendable
- SendableMetatype

