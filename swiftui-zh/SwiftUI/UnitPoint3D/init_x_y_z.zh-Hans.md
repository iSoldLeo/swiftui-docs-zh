---
来源：https://developer.apple.com/documentation/SwiftUI/UnitPoint3D/init(x:y:z:)
抓取时间：2025-12-01T11:24:46Z
---

# init(x:y:z:)

**Initializer**

以指定的偏移量创建一个 3D 单位点。

## 声明

```swift
init(x: CGFloat, y: CGFloat, z: CGFloat)
```

## 参数

- **x**：水平维度上从原点到点的归一化距离。
- **y**：从原点到垂直方向上的点的归一化距离。
- **z**：从原点到深度维度上的点的归一化距离。

### 讨论

超出 `[0, 1]` 范围的值会投影到视图以外的点。

## 创建点

- **init()**：在原点创建一个 3D 单位点。


---
source: https://developer.apple.com/documentation/SwiftUI/UnitPoint3D/init(x:y:z:)
crawled: 2025-12-01T11:24:46Z
---

# init(x:y:z:)

**Initializer**

Creates a 3D unit point with the specified offsets.

## Declaration

```swift
init(x: CGFloat, y: CGFloat, z: CGFloat)
```

## Parameters

- **x**: The normalized distance from the origin to the point in the horizontal dimension.
- **y**: The normalized distance from the origin to the point in the vertical dimension.
- **z**: The normalized distance from the origin to the point in the depth dimension.

## Discussion

Values outside the range `[0, 1]` project to points outside of a view.

## Creating a point

- **init()**: Creates a 3D unit point at the origin.

