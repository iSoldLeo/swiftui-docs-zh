---
来源： https://developer.apple.com/documentation/SwiftUI/GraphicsContext/clipBoundingRect
抓取时间：2025-12-02T20:58:18Z
---

# clipBoundingRect

**实例属性**

当前用户空间中所有当前剪辑形状交点的边界矩形。

## 声明

```swift
var clipBoundingRect: CGRect { get }
```

## 屏蔽

- **clip(to:style:options:)**：在上下文的剪辑形状数组中添加路径。
- **clipToLayer(opacity:options:content:)**：将您在新图层中定义的剪辑形状添加到上下文的剪辑形状数组中。
- **GraphicsContext.ClipOptions**：影响剪贴板形状使用的选项。


---
source: https://developer.apple.com/documentation/SwiftUI/GraphicsContext/clipBoundingRect
crawled: 2025-12-02T20:58:18Z
---

# clipBoundingRect

**Instance Property**

The bounding rectangle of the intersection of all current clip shapes in the current user space.

## Declaration

```swift
var clipBoundingRect: CGRect { get }
```

## Masking

- **clip(to:style:options:)**: Adds a path to the context’s array of clip shapes.
- **clipToLayer(opacity:options:content:)**: Adds a clip shape that you define in a new layer to the context’s array of clip shapes.
- **GraphicsContext.ClipOptions**: Options that affect the use of clip shapes.

