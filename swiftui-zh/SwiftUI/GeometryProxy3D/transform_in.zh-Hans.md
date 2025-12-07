---
来源： https://developer.apple.com/documentation/SwiftUI/GeometryProxy3D/transform(in:)
抓取时间： 2025-12-03T06:33:29Z
---

# transform(in:)

**实例方法**

将容器视图的三维变换转换到定义的坐标空间。

## 声明

```swift
func transform(in coordinateSpace: some CoordinateSpaceProtocol) -> AffineTransform3D?
```

## 讨论

如果视图没有定义明确的变换，例如受到投影变换的影响，此函数可能会返回 `nil`。

## 访问几何体特征

- **frame(in:)**：容器视图的边界矩形转换为定义的坐标空间。
- **size**：容器视图的大小。
- **safeAreaInsets**：容器视图的大小：容器视图的安全区域嵌入。
- **subscript(_:)**：容器视图的安全区域嵌入：确定容器视图中锚点的值。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryProxy3D/transform(in:)
crawled: 2025-12-03T06:33:29Z
---

# transform(in:)

**Instance Method**

The container view’s 3D transform converted to a defined coordinate space.

## Declaration

```swift
func transform(in coordinateSpace: some CoordinateSpaceProtocol) -> AffineTransform3D?
```

## Discussion

If the view doesn’t have a well-defined transform, such as if it’s affected by a projection transform, this function may return `nil`.

## Accessing geometry characteristics

- **frame(in:)**: The container view’s bounds rectangle converted to a defined coordinate space.
- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **subscript(_:)**: Resolves the value of an anchor to the container view.

