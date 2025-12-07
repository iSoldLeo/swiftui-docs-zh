---
来源：https://developer.apple.com/documentation/SwiftUI/Shape/trim(from:to:)
抓取时间： 2025-12-01T02:32:45Z
---

# trim(from:to:)

**实例方法**

根据该形状的路径表示法，以分数为单位修剪该形状。

## 声明

```swift
nonisolated func trim(from startFraction: CGFloat = 0, to endFraction: CGFloat = 1) -> some Shape

```

## 参数

- **startFraction**：绘制此图形时开始绘制的部分。
- **endFraction**：绘制此图形的过程中绘制结束的分数。

## 返回值

通过捕捉此形状的部分路径创建的形状。

## 讨论

要创建`Shape` 实例，需要使用直线和曲线定义形状的路径。使用 `trim(from:to:)` 方法可以忽略形状路径的起点和终点，从而绘制形状的一部分。

例如，如果您要从中心开始绘制一个数字 8 或无穷大符号 (∞)，将`startFraction` 和`endFraction` 设置为不同的值，就可以确定整体形状的部分。

下面的示例显示了一个简化的无穷大符号，它只绘制了整个形状的四分之三。也就是说，在符号的两个叶片中，一个叶片完整，另一个叶片只有一半完整。

```swift
Path { path in
    path.addLines([
        .init(x: 2, y: 1),
        .init(x: 1, y: 0),
        .init(x: 0, y: 1),
        .init(x: 1, y: 2),
        .init(x: 3, y: 0),
        .init(x: 4, y: 1),
        .init(x: 3, y: 2),
        .init(x: 2, y: 1)
    ])
}
.trim(from: 0.25, to: 1.0)
.scale(50, anchor: .topLeading)
.stroke(Color.black, lineWidth: 3)
```

将 `trim(from:to:)` 的参数更改为 `.trim(from: 0, to: 1)` 可以绘制完整的无穷符号，而 `.trim(from: 0, to: 0.5)` 则只能绘制符号的左叶。

## 变换形状

- **transform(_:)**：对形状进行仿射变换。
- **size(_:)**：返回代表相同形状的新版本 self，但要求它从`size` 的矩形创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **size(width:height:)**：返回表示相同形状的新版本 self，但要求它从`(width, height)` 大小的矩形中创建路径。这不会影响根据形状创建的任何视图的布局属性（例如通过填充）。
- **scale(_:anchor:)**：缩放此形状而不改变其边框。
- **scale(x:y:anchor:)**：缩放此形状而不改变其边框。
- **rotation(_:anchor:)**：以您指定的角度围绕锚点旋转此形状。
- **offset(_:)**：使用指定的点改变此形状的相对位置。
- **offset(x:y:)**：使用指定的点更改此形状的相对位置。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/trim(from:to:)
crawled: 2025-12-01T02:32:45Z
---

# trim(from:to:)

**Instance Method**

Trims this shape by a fractional amount based on its representation as a path.

## Declaration

```swift
nonisolated func trim(from startFraction: CGFloat = 0, to endFraction: CGFloat = 1) -> some Shape

```

## Parameters

- **startFraction**: The fraction of the way through drawing this shape where drawing starts.
- **endFraction**: The fraction of the way through drawing this shape where drawing ends.

## Return Value

A shape built by capturing a portion of this shape’s path.

## Discussion

To create a `Shape` instance, you define the shape’s path using lines and curves. Use the `trim(from:to:)` method to draw a portion of a shape by ignoring portions of the beginning and ending of the shape’s path.

For example, if you’re drawing a figure eight or infinity symbol (∞) starting from its center, setting the `startFraction` and `endFraction` to different values determines the parts of the overall shape.

The following example shows a simplified infinity symbol that draws only three quarters of the full shape. That is, of the two lobes of the symbol, one lobe is complete and the other is half complete.

```swift
Path { path in
    path.addLines([
        .init(x: 2, y: 1),
        .init(x: 1, y: 0),
        .init(x: 0, y: 1),
        .init(x: 1, y: 2),
        .init(x: 3, y: 0),
        .init(x: 4, y: 1),
        .init(x: 3, y: 2),
        .init(x: 2, y: 1)
    ])
}
.trim(from: 0.25, to: 1.0)
.scale(50, anchor: .topLeading)
.stroke(Color.black, lineWidth: 3)
```

Changing the parameters of `trim(from:to:)` to `.trim(from: 0, to: 1)` draws the full infinity symbol, while `.trim(from: 0, to: 0.5)` draws only the left lobe of the symbol.

## Transforming a shape

- **transform(_:)**: Applies an affine transform to this shape.
- **size(_:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of `size`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **size(width:height:)**: Returns a new version of self representing the same shape, but that will ask it to create its path from a rect of size `(width, height)`. This does not affect the layout properties of any views created from the shape (e.g. by filling it).
- **scale(_:anchor:)**: Scales this shape without changing its bounding frame.
- **scale(x:y:anchor:)**: Scales this shape without changing its bounding frame.
- **rotation(_:anchor:)**: Rotates this shape around an anchor point at the angle you specify.
- **offset(_:)**: Changes the relative position of this shape using the specified point.
- **offset(x:y:)**: Changes the relative position of this shape using the specified point.

