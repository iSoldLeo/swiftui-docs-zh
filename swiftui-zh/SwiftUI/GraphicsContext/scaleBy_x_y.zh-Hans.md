---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/scaleBy(x:y:)
抓取时间：2025-12-02T20:58:27Z
---

# scaleBy(x:y:)

**实例方法**

在每个维度上按一定量对后续绘图操作进行缩放。

## 声明

```swift
mutating func scaleBy(x: CGFloat, y: CGFloat)
```

## 参数

- **x**：水平方向上的缩放量。
- **y**：垂直方向上的缩放量。

## 讨论

调用此方法等同于使用给定的缩放因子直接更新上下文的[transform](transform.zh-Hans.md)：

```swift
transform = transform.scaledBy(x: x, y: y)
```

## 应用变换

- **rotate(by:)**：将后续绘图操作旋转一个角度。
- **translateBy(x:y:)**：将后续绘图操作在每个尺寸上移动一定量。
- **concatenate(_:)**：将给定的变换附加到上下文的现有变换中。
- **transform**：当前变换矩阵，定义用户空间坐标。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/scaleBy(x:y:)
crawled: 2025-12-02T20:58:27Z
---

# scaleBy(x:y:)

**Instance Method**

Scales subsequent drawing operations by an amount in each dimension.

## Declaration

```swift
mutating func scaleBy(x: CGFloat, y: CGFloat)
```

## Parameters

- **x**: The amount to scale in the horizontal direction.
- **y**: The amount to scale in the vertical direction.

## Discussion

Calling this method is equivalent to updating the context’s [transform](transform.zh-Hans.md) directly using the given scale factors:

```swift
transform = transform.scaledBy(x: x, y: y)
```

## Applying transforms

- **rotate(by:)**: Rotates subsequent drawing operations by an angle.
- **translateBy(x:y:)**: Moves subsequent drawing operations by an amount in each dimension.
- **concatenate(_:)**: Appends the given transform to the context’s existing transform.
- **transform**: The current transform matrix, defining user space coordinates.

