--- 来源：https://developer.apple.com/documentation/SwiftUI/GeometryProxy/subscript(_:)

抓取时间：2025-12-03T06:33:23Z

---

# subscript(_:)

**实例下标**

将锚点的值解析为容器视图。

## 声明

```swift
subscript<T>(anchor: Anchor<T>) -> T { get }
```

## 访问几何特征

- **bounds(of:)**：返回给定坐标空间的边界矩形，并转换为局部坐标空间。

- **frame(in:)**：返回容器视图的边界矩形，并转换为已定义的坐标空间。

- **size**：容器视图的大小。

- **safeAreaInsets**：容器视图的安全区域内边距。

- **transform(in:)**：容器视图的三维变换已转换为指定的坐标空间。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryProxy/subscript(_:)
crawled: 2025-12-03T06:33:23Z
---

# subscript(_:)

**Instance Subscript**

Resolves the value of an anchor to the container view.

## Declaration

```swift
subscript<T>(anchor: Anchor<T>) -> T { get }
```

## Accessing geometry characteristics

- **bounds(of:)**: Returns the given coordinate space’s bounds rectangle, converted to the local coordinate space.
- **frame(in:)**: Returns the container view’s bounds rectangle, converted to a defined coordinate space.
- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **transform(in:)**: The container view’s 3D transform converted to a defined coordinate space.

