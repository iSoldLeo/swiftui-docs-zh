---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/translateBy(x:y:)
抓取时间：2025-12-02T20:58:28Z
---

# translateBy(x:y:)

**实例方法**

将后续绘图操作在每个维度上移动一定量。

## 声明

```swift
mutating func translateBy(x: CGFloat, y: CGFloat)
```

## 参数

- **x**：沿水平方向移动的量。
- **y**：垂直方向的移动量。

## 讨论

调用此方法等同于使用给定的平移量直接更新上下文的[transform](transform.zh-Hans.md)：

```swift
transform = transform.translatedBy(x: x, y: y)
```

## 应用转换

- **scaleBy(x:y:)**：在每个维度上对后续绘图操作进行缩放。
- **rotate(by:)**：将后续绘图操作旋转一个角度。
- **concatenate(_:)**：将给定的变换附加到上下文的现有变换中。
- **transform**：当前变换矩阵，定义用户空间坐标。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/translateBy(x:y:)
crawled: 2025-12-02T20:58:28Z
---

# translateBy(x:y:)

**Instance Method**

Moves subsequent drawing operations by an amount in each dimension.

## Declaration

```swift
mutating func translateBy(x: CGFloat, y: CGFloat)
```

## Parameters

- **x**: The amount to move in the horizontal direction.
- **y**: The amount to move in the vertical direction.

## Discussion

Calling this method is equivalent to updating the context’s [transform](transform.zh-Hans.md) directly using the given translation amount:

```swift
transform = transform.translatedBy(x: x, y: y)
```

## Applying transforms

- **scaleBy(x:y:)**: Scales subsequent drawing operations by an amount in each dimension.
- **rotate(by:)**: Rotates subsequent drawing operations by an angle.
- **concatenate(_:)**: Appends the given transform to the context’s existing transform.
- **transform**: The current transform matrix, defining user space coordinates.

