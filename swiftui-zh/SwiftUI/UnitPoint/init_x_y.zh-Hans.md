---
来源：https://developer.apple.com/documentation/SwiftUI/UnitPoint/init(x:y:)
抓取时间： 2025-12-01T11:24:27Z
---

# init(x:y:)

**Initializer**

以指定的水平和垂直偏移量创建单位点。

## 声明

```swift
init(x: CGFloat, y: CGFloat)
```

## 参数

- **x**：水平方向上从原点到点的归一化距离。
- **y**：从原点到点在垂直方向上的归一化距离。

### 讨论

超出 `[0, 1]` 范围的值会投影到视图以外的点。

## 创建点

- **init()**：在原点创建一个单位点。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitPoint/init(x:y:)
crawled: 2025-12-01T11:24:27Z
---

# init(x:y:)

**Initializer**

Creates a unit point with the specified horizontal and vertical offsets.

## Declaration

```swift
init(x: CGFloat, y: CGFloat)
```

## Parameters

- **x**: The normalized distance from the origin to the point in the horizontal direction.
- **y**: The normalized distance from the origin to the point in the vertical direction.

## Discussion

Values outside the range `[0, 1]` project to points outside of a view.

## Creating a point

- **init()**: Creates a unit point at the origin.

