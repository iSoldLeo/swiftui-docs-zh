---
来源： https://developer.apple.com/documentation/SwiftUI/GeometryProxy3D/subscript(_:)
抓取时间： 2025-12-01T11:22:38Z
---

# 下标(_:)

**实例下标**

将锚点的值转换为容器视图的值。

## 声明

```swift
subscript<T>(anchor: Anchor<T>) -> T { get }
```

## 访问几何特征

- **frame(in:)**：容器视图的边界矩形转换为定义的坐标空间。
- **size**：容器视图的大小。
- **safeAreaInsets**：容器视图的安全区域嵌入。
- **transform(in:)**：将容器视图的 3D 变换转换到定义的坐标空间。


---
source: https://developer.apple.com/documentation/SwiftUI/GeometryProxy3D/subscript(_:)
crawled: 2025-12-01T11:22:38Z
---

# subscript(_:)

**Instance Subscript**

Resolves the value of an anchor to the container view.

## Declaration

```swift
subscript<T>(anchor: Anchor<T>) -> T { get }
```

## Accessing geometry characteristics

- **frame(in:)**: The container view’s bounds rectangle converted to a defined coordinate space.
- **size**: The size of the container view.
- **safeAreaInsets**: The safe area inset of the container view.
- **transform(in:)**: The container view’s 3D transform converted to a defined coordinate space.

