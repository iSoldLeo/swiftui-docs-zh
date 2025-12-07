--- 来源：https://developer.apple.com/documentation/SwiftUI/GeometryProxy/frame(in:)

抓取时间：2025-12-01T11:22:29Z

---

# frame(in:)

**实例方法**

返回容器视图的边界矩形，并转换为已定义的坐标空间。

## 声明

```swift
func frame(in coordinateSpace: some CoordinateSpaceProtocol) -> CGRect
```

## 访问几何特征

- **bounds(of:)**：返回给定坐标空间的边界矩形，并转换为局部坐标空间。

- **size**：容器视图的大小。

- **safeAreaInsets**：容器视图的安全区域内边距。

- **subscript(_:)**：将锚点的值解析为容器视图。

- **transform(in:)**：容器视图的三维变换已转换为指定的坐标空间。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryProxy/frame(in:)
crawled: 2025-12-01T11:22:29Z
---

# frame(in:)

**Instance Method**

Returns the container view’s bounds rectangle, converted to a defined coordinate space.

## Declaration

```swift
func frame(in coordinateSpace: some CoordinateSpaceProtocol) -> CGRect
```

## Accessing geometry characteristics

- **bounds(of:)**: Returns the given coordinate space’s bounds rectangle, converted to the local coordinate space.
- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **subscript(_:)**: Resolves the value of an anchor to the container view.
- **transform(in:)**: The container view’s 3D transform converted to a defined coordinate space.

