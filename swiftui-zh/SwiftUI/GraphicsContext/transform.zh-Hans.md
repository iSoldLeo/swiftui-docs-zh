---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/transform
抓取时间：2025-12-02T20:58:30Z
---

# 转换

**实例属性**

当前变换矩阵，定义用户空间坐标。

## 声明

```swift
var transform: CGAffineTransform { get set }
```

## 讨论

修改此矩阵可转换您随后绘制到上下文中的内容。您所做的更改不会影响现有内容。

## 应用变换

- **scaleBy(x:y:)**：在每个维度上按一定量缩放后续绘图操作。
- **rotate(by:)**：将后续绘图操作旋转一个角度。
- **translateBy(x:y:)**：将后续绘图操作在每个尺寸上移动一定量。
- **concatenate(_:)**：将给定的变换附加到上下文的现有变换中。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/transform
crawled: 2025-12-02T20:58:30Z
---

# transform

**Instance Property**

The current transform matrix, defining user space coordinates.

## Declaration

```swift
var transform: CGAffineTransform { get set }
```

## Discussion

Modify this matrix to transform content that you subsequently draw into the context. Changes that you make don’t affect existing content.

## Applying transforms

- **scaleBy(x:y:)**: Scales subsequent drawing operations by an amount in each dimension.
- **rotate(by:)**: Rotates subsequent drawing operations by an angle.
- **translateBy(x:y:)**: Moves subsequent drawing operations by an amount in each dimension.
- **concatenate(_:)**: Appends the given transform to the context’s existing transform.

