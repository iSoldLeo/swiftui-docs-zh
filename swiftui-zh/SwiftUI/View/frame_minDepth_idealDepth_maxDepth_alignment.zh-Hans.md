--- 来源：https://developer.apple.com/documentation/SwiftUI/View/frame(minDepth:idealDepth:maxDepth:alignment:)

抓取时间：2025-12-02T16:21:23Z

---

# frame(minDepth:idealDepth:maxDepth:alignment:)

**实例方法**

将此视图定位到一个具有指定深度约束的不可见框架内。

## 声明

```swift
nonisolated func frame(minDepth: CGFloat? = nil, idealDepth: CGFloat? = nil, maxDepth: CGFloat? = nil, alignment: DepthAlignment = .center) -> some View

```

## 参数

- **minDepth**：生成的框架的最小深度。

- **idealDepth**：生成的框架的理想深度。

- **maxDepth**：生成的框架的最大深度。

- **alignment**：此视图在生成的框架内的对齐方式。请注意，当框架的大小恰好与此视图的大小匹配时，大多数对齐值不会产生明显的影响。

## 返回值

一个具有灵活尺寸的视图，其尺寸由调用中非 `nil` 参数指定。

## 说明

调用此方法时，务必至少指定一个尺寸特征。传递 `nil` 或省略某个特征，以指示框架应采用此视图的尺寸行为，但受其他非 `nil` 参数的约束。

建议给此视图的尺寸是建议给框架的尺寸，受任何指定的约束限制，并且使用指定的理想尺寸替换建议中任何相应的未指定尺寸。

如果在给定尺寸中未指定最小或最大约束，则框架在该尺寸上采用其子视图的尺寸行为。如果在某个维度上同时指定了两个约束条件，则框架将无条件地采用其建议的尺寸，但会受到约束条件的限制。否则，框架在任一维度上的尺寸将按以下方式调整：

- 如果指定了最小约束条件，且父级框架建议的尺寸小于此视图的尺寸，则框架尺寸将限制为建议的最小尺寸。

- 如果指定了最大约束条件，且父级框架建议的尺寸大于此视图的尺寸，则框架尺寸将限制为建议的最大值。

- 否则，框架尺寸将保持不变。

## 影响视图尺寸

- **frame(width:height:alignment:)**：将此视图定位在具有指定尺寸的不可见框架内。

- **frame(depth:alignment:)**：将此视图定位在具有指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图定位在具有指定尺寸约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **fixedSize()**：将此视图固定在理想尺寸。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想尺寸。

- **layoutPriority(_:)**：设置父布局分配给此子布局空间的优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/frame(minDepth:idealDepth:maxDepth:alignment:)
crawled: 2025-12-02T16:21:23Z
---

# frame(minDepth:idealDepth:maxDepth:alignment:)

**Instance Method**

Positions this view within an invisible frame having the specified depth constraints.

## Declaration

```swift
nonisolated func frame(minDepth: CGFloat? = nil, idealDepth: CGFloat? = nil, maxDepth: CGFloat? = nil, alignment: DepthAlignment = .center) -> some View

```

## Parameters

- **minDepth**: The minimum depth of the resulting frame.
- **idealDepth**: The ideal depth of the resulting frame.
- **maxDepth**: The maximum depth of the resulting frame.
- **alignment**: The alignment of this view inside the resulting frame. Note that most alignment values have no apparent effect when the size of the frame happens to match that of this view.

## Return Value

A view with flexible dimensions given by the call’s non-`nil` parameters.

## Discussion

Always specify at least one size characteristic when calling this method. Pass `nil` or leave out a characteristic to indicate that the frame should adopt this view’s sizing behavior, constrained by the other non-`nil` arguments.

The size proposed to this view is the size proposed to the frame, limited by any constraints specified, and with an ideal dimension specified replacing any corresponding unspecified dimensions in the proposal.

If no minimum or maximum constraint is specified in a given dimension, the frame adopts the sizing behavior of its child in that dimension. If both constraints are specified in a dimension, the frame unconditionally adopts the size proposed for it, clamped to the constraints. Otherwise, the size of the frame in either dimension is:

- If a minimum constraint is specified and the size proposed for the frame by the parent is less than the size of this view, the proposed size, clamped to that minimum.
- If a maximum constraint is specified and the size proposed for the frame by the parent is greater than the size of this view, the proposed size, clamped to that maximum.
- Otherwise, the size of this view.

## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

