--- 来源：https://developer.apple.com/documentation/SwiftUI/View/frame(depth:alignment:)

抓取时间：2025-12-02T17:38:35Z

---

# frame(depth:alignment:)

**实例方法**

将此视图定位到指定深度的不可见框架内。

## 声明

```swift
nonisolated func frame(depth: CGFloat?, alignment: DepthAlignment = .center) -> some View

```

## 参数

- **depth**：生成的视图的固定深度。如果 `depth` 为 `nil`，则生成的视图将采用此视图的尺寸行为。

- **alignment**：此视图在生成的视图中的对齐方式。如果此视图小于生成的框架所指定的尺寸，则应用 `alignment`。

## 返回值

如果视图不为 `nil`，则返回尺寸固定为 `depth` 的视图。

## 说明

使用此方法可指定视图深度的固定尺寸。如果未指定尺寸，则生成的视图将沿用此视图的深度缩放行为。

## 影响视图尺寸

- **frame(width:height:alignment:)**：将此视图放置在具有指定尺寸的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图放置在具有指定尺寸约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图放置在具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图放置在相对于最近容器的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **fixedSize()**：将此视图固定在理想大小。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想大小。

- **layoutPriority(_:)**：设置父布局分配给此子布局空间的优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/frame(depth:alignment:)
crawled: 2025-12-02T17:38:35Z
---

# frame(depth:alignment:)

**Instance Method**

Positions this view within an invisible frame with the specified depth.

## Declaration

```swift
nonisolated func frame(depth: CGFloat?, alignment: DepthAlignment = .center) -> some View

```

## Parameters

- **depth**: A fixed depth for the resulting view. If `depth` is `nil`, the resulting view assumes this view’s sizing behavior.
- **alignment**: The alignment of this view inside the resulting view. `alignment` applies if this view is smaller than the size given by the resulting frame.

## Return Value

A view with a fixed dimension of `depth` if non-`nil`.

## Discussion

Use this method to specify a fixed size for a view’s depth. If you don’t specify a dimension, the resulting view assumes this view’s sizing behavior in depth.

## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

