--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fixedSize()

抓取时间：2025-12-02T17:38:38Z

---

# fixedSize()

**实例方法**

将此视图固定为理想大小。

## 声明

```swift
nonisolated func fixedSize() -> some View

```

## 返回值

一个固定了此视图大小的视图。

## 说明

在视图层级布局过程中，每个视图都会向其包含的每个子视图提出一个大小建议。如果子视图不需要固定大小，则可以接受并遵循父视图提供的大小。

例如，放置在显式指定大小的框架中的 [Text](../Text.zh-Hans.md) 视图会换行并截断其字符串，以保持在父视图的边界内：

```swift
Text("A single line of text, too long to fit in a box.")
    .frame(width: 200, height: 200)
    .border(Color.gray)
```

`fixedSize()` 修饰符可用于创建视图，使其在两个维度上都保持子视图的*理想大小*：

```swift
Text("A single line of text, too long to fit in a box.")
    .fixedSize()
    .frame(width: 200, height: 200)
    .border(Color.gray)
```

这可能会导致视图超出父视图的边界，而这可能并非您想要的效果。

您可以将 `fixedSize()` 理解为针对父视图提出的视图大小创建*反向提议*。视图的理想大小以及 `fixedSize()` 的具体效果取决于具体的视图及其配置方式。

要创建固定视图水平或垂直尺寸的视图，请参阅 [fixedSize(horizontal:vertical:)](fixedSize_horizontal_vertical.zh-Hans.md)。

## 影响视图尺寸

- **frame(width:height:alignment:)**：将此视图放置在指定尺寸的不可见框架内。

- **frame(depth:alignment:)**：将此视图放置在指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图放置在具有指定尺寸约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图放置在具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图放置在相对于最近容器的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图放置在相对于最近容器的不可见框架内。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想大小。

- **layoutPriority(_:)**：设置父布局分配给此子布局空间的优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fixedSize()
crawled: 2025-12-02T17:38:38Z
---

# fixedSize()

**Instance Method**

Fixes this view at its ideal size.

## Declaration

```swift
nonisolated func fixedSize() -> some View

```

## Return Value

A view that fixes this view at its ideal size.

## Discussion

During the layout of the view hierarchy, each view proposes a size to each child view it contains. If the child view doesn’t need a fixed size it can accept and conform to the size offered by the parent.

For example, a [Text](../Text.zh-Hans.md) view placed in an explicitly sized frame wraps and truncates its string to remain within its parent’s bounds:

```swift
Text("A single line of text, too long to fit in a box.")
    .frame(width: 200, height: 200)
    .border(Color.gray)
```



The `fixedSize()` modifier can be used to create a view that maintains the *ideal size* of its children both dimensions:

```swift
Text("A single line of text, too long to fit in a box.")
    .fixedSize()
    .frame(width: 200, height: 200)
    .border(Color.gray)
```

This can result in the view exceeding the parent’s bounds, which may or may not be the effect you want.



You can think of `fixedSize()` as the creation of a *counter proposal* to the view size proposed to a view by its parent. The ideal size of a view, and the specific effects of `fixedSize()` depends on the particular view and how you have configured it.

To create a view that fixes the view’s size in either the horizontal or vertical dimensions, see [fixedSize(horizontal:vertical:)](fixedSize_horizontal_vertical.zh-Hans.md).

## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

