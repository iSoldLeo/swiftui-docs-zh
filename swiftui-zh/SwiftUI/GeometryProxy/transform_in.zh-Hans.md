--- 来源：https://developer.apple.com/documentation/SwiftUI/GeometryProxy/transform(in:)

抓取时间：2025-12-01T11:22:33Z

---

# transform(in:)

**实例方法**

将容器视图的 3D 变换转换为已定义的坐标空间。

## 声明

```swift
func transform(in coordinateSpace: some CoordinateSpaceProtocol) -> AffineTransform3D?
```

## 说明

如果视图没有明确定义的变换（例如，受投影变换影响），则此函数可能返回 `nil`。

## 访问几何特征

- **bounds(of:)**：返回给定坐标空间的边界矩形，并将其转换为局部坐标空间。

- **frame(in:)**：返回容器视图的边界矩形，并将其转换为已定义的坐标空间。

- **size**：容器视图的大小。

- **safeAreaInsets**：容器视图的安全区域内边距。

- **subscript(_:)**：将锚点的值解析为容器视图的值。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryProxy/transform(in:)
crawled: 2025-12-01T11:22:33Z
---

# transform(in:)

**Instance Method**

The container view’s 3D transform converted to a defined coordinate space.

## Declaration

```swift
func transform(in coordinateSpace: some CoordinateSpaceProtocol) -> AffineTransform3D?
```

## Discussion

If the view doesn’t have a well defined transform, such as if it is affected by a projection transform, this function may return `nil`.

## Accessing geometry characteristics

- **bounds(of:)**: Returns the given coordinate space’s bounds rectangle, converted to the local coordinate space.
- **frame(in:)**: Returns the container view’s bounds rectangle, converted to a defined coordinate space.
- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **subscript(_:)**: Resolves the value of an anchor to the container view.

