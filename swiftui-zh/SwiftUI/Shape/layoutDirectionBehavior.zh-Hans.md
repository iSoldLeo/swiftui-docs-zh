---
来源： https://developer.apple.com/documentation/SwiftUI/Shape/layoutDirectionBehavior
抓取时间： 2025-12-02T21:42:00Z
---

# 布局方向行为

**实例属性**

返回此形状在不同布局方向上应使用的行为。

## 声明

```swift
nonisolated var layoutDirectionBehavior: LayoutDirectionBehavior { get }
```

## 讨论

如果形状的布局方向行为（layoutDirectionBehavior）是镜像，那么在指定的布局方向上，形状的路径将被水平镜像。镜像时，路径上的各个点将发生转换。

在 iOS 17.0、macOS 14.0、tvOS 17.0、watchOS 10.0 及更高版本上部署时默认为`.mirrors`，否则默认为`.fixed`。要在部署到早期版本时镜像路径，可以对填充或描边形状使用 `View.flipsForRightToLeftLayoutDirection`，或有条件地镜像形状路径中的点。


---
source: https://developer.apple.com/documentation/SwiftUI/Shape/layoutDirectionBehavior
crawled: 2025-12-02T21:42:00Z
---

# layoutDirectionBehavior

**Instance Property**

Returns the behavior this shape should use for different layout directions.

## Declaration

```swift
nonisolated var layoutDirectionBehavior: LayoutDirectionBehavior { get }
```

## Discussion

If the layoutDirectionBehavior for a Shape is one that mirrors, the shape’s path will be mirrored horizontally when in the specified layout direction. When mirrored, the individual points of the path will be transformed.

Defaults to `.mirrors` when deploying on iOS 17.0, macOS 14.0, tvOS 17.0, watchOS 10.0 and later, and to `.fixed` if not. To mirror a path when deploying to earlier releases, either use `View.flipsForRightToLeftLayoutDirection` for a filled or stroked shape or conditionally mirror the points in the path of the shape.

