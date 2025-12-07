---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/concatenate(_:)
抓取时间： 2025-12-02T20:58:29Z
---

# concatenate(_:)

**实例方法**

将给定的变换添加到上下文的现有变换中。

## 声明

```swift
mutating func concatenate(_ matrix: CGAffineTransform)
```

## 参数

- **matrix**：要追加到现有变换中的变换。

## 讨论

调用此方法等同于直接使用`matrix` 参数更新上下文的[transform](transform.zh-Hans.md)：

```swift
transform = matrix.concatenating(transform)
```

## 应用变换

- **scaleBy(x:y:)**：在每个维度上对后续绘图操作进行缩放。
- **rotate(by:)**：将后续绘图操作旋转一个角度。
- **translateBy(x:y:)**：将后续绘图操作在每个尺寸上移动一定量。
- **transform**：当前变换矩阵，定义用户空间坐标。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/concatenate(_:)
crawled: 2025-12-02T20:58:29Z
---

# concatenate(_:)

**Instance Method**

Appends the given transform to the context’s existing transform.

## Declaration

```swift
mutating func concatenate(_ matrix: CGAffineTransform)
```

## Parameters

- **matrix**: A transform to append to the existing transform.

## Discussion

Calling this method is equivalent to updating the context’s [transform](transform.zh-Hans.md) directly using the `matrix` parameter:

```swift
transform = matrix.concatenating(transform)
```

## Applying transforms

- **scaleBy(x:y:)**: Scales subsequent drawing operations by an amount in each dimension.
- **rotate(by:)**: Rotates subsequent drawing operations by an angle.
- **translateBy(x:y:)**: Moves subsequent drawing operations by an amount in each dimension.
- **transform**: The current transform matrix, defining user space coordinates.

