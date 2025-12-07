---
来源：https://developer.apple.com/documentation/SwiftUI/GraphicsContext/rotate(作者：)
抓取时间：2025-12-02T20:58:27Z
---

# rotate(by:)

**实例方法**

将后续绘图操作旋转一个角度。

## 声明

```swift
mutating func rotate(by angle: Angle)
```

## 参数

- **angle**：要旋转的量。

## 讨论

调用此方法等同于直接使用`angle`参数更新上下文的[transform](transform.zh-Hans.md)：

```swift
transform = transform.rotated(by: angle.radians)
```

## 应用变换

- **scaleBy(x:y:)**：在每个维度上对后续绘图操作进行缩放。
- **translateBy(x:y:)**：在各尺寸中按一定量移动后续绘图操作。
- **concatenate(_:)**：将给定的变换附加到上下文的现有变换中。
- **transform**：当前变换矩阵，定义用户空间坐标。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/rotate(by:)
crawled: 2025-12-02T20:58:27Z
---

# rotate(by:)

**Instance Method**

Rotates subsequent drawing operations by an angle.

## Declaration

```swift
mutating func rotate(by angle: Angle)
```

## Parameters

- **angle**: The amount to rotate.

## Discussion

Calling this method is equivalent to updating the context’s [transform](transform.zh-Hans.md) directly using the `angle` parameter:

```swift
transform = transform.rotated(by: angle.radians)
```

## Applying transforms

- **scaleBy(x:y:)**: Scales subsequent drawing operations by an amount in each dimension.
- **translateBy(x:y:)**: Moves subsequent drawing operations by an amount in each dimension.
- **concatenate(_:)**: Appends the given transform to the context’s existing transform.
- **transform**: The current transform matrix, defining user space coordinates.

