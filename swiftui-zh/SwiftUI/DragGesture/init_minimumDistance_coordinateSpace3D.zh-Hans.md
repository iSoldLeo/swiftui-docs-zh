---
来源：https://developer.apple.com/documentation/SwiftUI/DragGesture/init(minimumDistance:coordinateSpace3D:)
抓取时间：2025-12-01T02:38:07Z
---

# init(minimumDistance:coordinateSpace3D:)

**Initializer**

创建拖动手势，并设置手势成功前的最小拖动距离和手势位置的坐标空间。

### 声明

```swift
init(minimumDistance: CGFloat = 0, coordinateSpace3D: some CoordinateSpace3D)
```

## 参数

- **minimumDistance**：手势成功拖动的最小距离。确保该单位与提供的 `CoordinateSpace3D`缩放比例相同，默认值为 0，以避免不同坐标空间缩放比例引起的问题。
- **coordinateSpace3D**：拖动手势位置的三维坐标空间。


---
source: https://developer.apple.com/documentation/SwiftUI/DragGesture/init(minimumDistance:coordinateSpace3D:)
crawled: 2025-12-01T02:38:07Z
---

# init(minimumDistance:coordinateSpace3D:)

**Initializer**

Creates a dragging gesture with the minimum dragging distance before the gesture succeeds and the coordinate space of the gesture’s location.

## Declaration

```swift
init(minimumDistance: CGFloat = 0, coordinateSpace3D: some CoordinateSpace3D)
```

## Parameters

- **minimumDistance**: The minimum dragging distance for the gesture to succeed. Ensure this unit is in the same scale as the provided `CoordinateSpace3D`, the default value is 0 to avoid issues around differing coordinate space scales.
- **coordinateSpace3D**: The coordinate space 3D of the dragging gesture’s location.

