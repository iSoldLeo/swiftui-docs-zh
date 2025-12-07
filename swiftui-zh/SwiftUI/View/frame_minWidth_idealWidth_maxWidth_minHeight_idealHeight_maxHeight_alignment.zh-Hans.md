--- 来源：https://developer.apple.com/documentation/SwiftUI/View/frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)

抓取时间：2025-12-02T17:38:36Z

---

# frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)

**实例方法**

将此视图定位到一个具有指定尺寸约束的不可见框架内。

## 声明

```swift
nonisolated func frame(minWidth: CGFloat? = nil, idealWidth: CGFloat? = nil, maxWidth: CGFloat? = nil, minHeight: CGFloat? = nil, idealHeight: CGFloat? = nil, maxHeight: CGFloat? = nil, alignment: Alignment = .center) -> some View

```

## 参数

- **minWidth**：生成的框架的最小宽度。

- **idealWidth**：生成的框架的理想宽度。

- **maxWidth**：生成的框架的最大宽度。

- **minHeight**：生成的框架的最小高度。

- **idealHeight**：生成的框架的理想高度。

- **maxHeight**：生成的框架的最大高度。

- **alignment**：此视图在生成的框架内的对齐方式。请注意，当框架的大小恰好与此视图的大小匹配时，大多数对齐值不会产生明显的影响。

## 返回值

返回一个视图，其尺寸由调用中非 `nil` 参数指定。

## 说明

调用此方法时，请始终至少指定一个尺寸特征。传递 `nil` 或省略某个特征，以指示框架应采用此视图的尺寸行为，但受其他非 `nil` 参数的约束。

此视图建议的尺寸是框架建议的尺寸，受任何指定的约束限制，并且任何指定的理想尺寸都会替换建议尺寸中任何对应的未指定尺寸。

如果在给定尺寸中未指定最小或最大约束，则框架在该尺寸上采用其子视图的尺寸行为。如果在某个尺寸中同时指定了最小和最大约束，则框架无条件地采用为其建议的尺寸，但会受到约束的限制。否则，框架在任一尺寸上的尺寸为：

- 如果指定了最小约束，并且父视图为框架建议的尺寸小于此视图的尺寸，则为建议尺寸，但限制为该最小值。

- 如果指定了最大约束，并且父视图为框架建议的尺寸大于此视图的尺寸，则为建议尺寸，但限制为该最大值。

- 否则，为此视图的尺寸。

## 影响视图的尺寸

- **frame(width:height:alignment:)**：将此视图定位在具有指定尺寸的不可见框架内。

- **frame(depth:alignment:)**：将此视图定位在具有指定深度的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图定位在具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图定位在相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在相对于最近容器大小的不可见框架内。

- **fixedSize()**：将此视图固定在其理想大小。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想大小。

- **layoutPriority(_:)**：设置父布局向子布局分配空间的优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)
crawled: 2025-12-02T17:38:36Z
---

# frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)

**Instance Method**

Positions this view within an invisible frame having the specified size constraints.

## Declaration

```swift
nonisolated func frame(minWidth: CGFloat? = nil, idealWidth: CGFloat? = nil, maxWidth: CGFloat? = nil, minHeight: CGFloat? = nil, idealHeight: CGFloat? = nil, maxHeight: CGFloat? = nil, alignment: Alignment = .center) -> some View

```

## Parameters

- **minWidth**: The minimum width of the resulting frame.
- **idealWidth**: The ideal width of the resulting frame.
- **maxWidth**: The maximum width of the resulting frame.
- **minHeight**: The minimum height of the resulting frame.
- **idealHeight**: The ideal height of the resulting frame.
- **maxHeight**: The maximum height of the resulting frame.
- **alignment**: The alignment of this view inside the resulting frame. Note that most alignment values have no apparent effect when the size of the frame happens to match that of this view.

## Return Value

A view with flexible dimensions given by the call’s non-`nil` parameters.

## Discussion

Always specify at least one size characteristic when calling this method. Pass `nil` or leave out a characteristic to indicate that the frame should adopt this view’s sizing behavior, constrained by the other non-`nil` arguments.

The size proposed to this view is the size proposed to the frame, limited by any constraints specified, and with any ideal dimensions specified replacing any corresponding unspecified dimensions in the proposal.

If no minimum or maximum constraint is specified in a given dimension, the frame adopts the sizing behavior of its child in that dimension. If both constraints are specified in a dimension, the frame unconditionally adopts the size proposed for it, clamped to the constraints. Otherwise, the size of the frame in either dimension is:

- If a minimum constraint is specified and the size proposed for the frame by the parent is less than the size of this view, the proposed size, clamped to that minimum.
- If a maximum constraint is specified and the size proposed for the frame by the parent is greater than the size of this view, the proposed size, clamped to that maximum.
- Otherwise, the size of this view.

## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

