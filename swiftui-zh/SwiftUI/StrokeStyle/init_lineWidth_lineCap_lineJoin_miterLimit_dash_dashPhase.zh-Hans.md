--- 来源：https://developer.apple.com/documentation/SwiftUI/StrokeStyle/init(lineWidth:lineCap:lineJoin:miterLimit:dash:dashPhase:)

抓取时间：2025-12-03T06:24:31Z

---

# init(lineWidth:lineCap:lineJoin:miterLimit:dash:dashPhase:)

**Initializer**

根据给定的组件创建新的描边样式。

## 声明

```swift
init(lineWidth: CGFloat = 1, lineCap: CGLineCap = .butt, lineJoin: CGLineJoin = .miter, miterLimit: CGFloat = 10, dash: [CGFloat] = [CGFloat](), dashPhase: CGFloat = 0)
```

## 参数

- **lineWidth**：线段的宽度。

- **lineCap**：线段的端点样式。

- **lineJoin**：线段的连接类型。

- **miterLimit**：用于确定接合处是否使用斜角而非斜接的阈值。

- **dash**：用于绘制虚线的涂漆线段和未涂漆线段的长度。

- **dashPhase**：虚线从虚线图案的哪个位置开始。


---
source: https://developer.apple.com/documentation/SwiftUI/StrokeStyle/init(lineWidth:lineCap:lineJoin:miterLimit:dash:dashPhase:)
crawled: 2025-12-03T06:24:31Z
---

# init(lineWidth:lineCap:lineJoin:miterLimit:dash:dashPhase:)

**Initializer**

Creates a new stroke style from the given components.

## Declaration

```swift
init(lineWidth: CGFloat = 1, lineCap: CGLineCap = .butt, lineJoin: CGLineJoin = .miter, miterLimit: CGFloat = 10, dash: [CGFloat] = [CGFloat](), dashPhase: CGFloat = 0)
```

## Parameters

- **lineWidth**: The width of the segment.
- **lineCap**: The endpoint style of a segment.
- **lineJoin**: The join type of a segment.
- **miterLimit**: The threshold used to determine whether to use a bevel instead of a miter at a join.
- **dash**: The lengths of painted and unpainted segments used to make a dashed line.
- **dashPhase**: How far into the dash pattern the line starts.

