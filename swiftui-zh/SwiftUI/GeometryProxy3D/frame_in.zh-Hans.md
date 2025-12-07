---
来源： https://developer.apple.com/documentation/SwiftUI/GeometryProxy3D/frame(in:)
抓取时间： 2025-12-01T11:22:34Z
---

# frame(in:)

**实例方法**

将容器视图的边界矩形转换为定义的坐标空间。

## 声明

```swift
func frame(in coordinateSpace: some CoordinateSpaceProtocol) -> Rect3D
```

## 访问几何特征

- **size**：容器视图的尺寸。
- **safeAreaInsets**：容器视图的安全区域嵌入。
- **subscript(_:)**：容器视图的安全区域嵌入：确定容器视图中锚点的值。
- **transform(in:)**：将容器视图的 3D 变换转换到定义的坐标空间。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryProxy3D/frame(in:)
crawled: 2025-12-01T11:22:34Z
---

# frame(in:)

**Instance Method**

The container view’s bounds rectangle converted to a defined coordinate space.

## Declaration

```swift
func frame(in coordinateSpace: some CoordinateSpaceProtocol) -> Rect3D
```

## Accessing geometry characteristics

- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **subscript(_:)**: Resolves the value of an anchor to the container view.
- **transform(in:)**: The container view’s 3D transform converted to a defined coordinate space.

