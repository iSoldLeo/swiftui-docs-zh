--- 来源：https://developer.apple.com/documentation/SwiftUI/View/fixedSize(horizontal:vertical:)

抓取时间：2025-12-02T17:38:39Z

---

# fixedSize(horizontal:vertical:)

**实例方法**

将此视图固定在指定尺寸的理想大小。

## 声明

```swift
nonisolated func fixedSize(horizontal: Bool, vertical: Bool) -> some View

```

## 参数

- **horizontal**：一个布尔值，指示是否固定视图的宽度。

- **vertical**：一个布尔值，指示是否固定视图的高度。

## 返回值

返回一个视图，该视图将自身固定在由 `horizontal` 和 `vertical` 指定的尺寸范围内。

## 说明

此函数的行为与 [fixedSize()](fixedSize.zh-Hans.md) 类似，不同之处在于，使用 `fixedSize(horizontal:vertical:)` 时，可以选择在一个或两个维度上固定坐标轴。例如，如果在将文本视图包裹到框架视图之前水平固定其大小，则相当于告诉文本视图保持其理想的*宽度*。视图会计算出表示整个字符串所需的空间。

```swift
Text("A single line of text, too long to fit in a box.")
    .fixedSize(horizontal: true, vertical: false)
    .frame(width: 200, height: 200)
    .border(Color.gray)
```

这可能会导致视图超出父视图的边界，而这可能并非您想要的效果。

## 影响视图的大小

- **frame(width:height:alignment:)**：将此视图定位在具有指定大小的不可见框架内。

- **frame(depth:alignment:)**：将此视图定位在具有指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图定位在具有指定尺寸约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图定位在具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图定位在相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在相对于最近容器大小的不可见框架内。

- **fixedSize()**：将此视图固定为理想大小。

- **layoutPriority(_:)**：设置父布局向子布局分配空间的优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/fixedSize(horizontal:vertical:)
crawled: 2025-12-02T17:38:39Z
---

# fixedSize(horizontal:vertical:)

**Instance Method**

Fixes this view at its ideal size in the specified dimensions.

## Declaration

```swift
nonisolated func fixedSize(horizontal: Bool, vertical: Bool) -> some View

```

## Parameters

- **horizontal**: A Boolean value that indicates whether to fix the width of the view.
- **vertical**: A Boolean value that indicates whether to fix the height of the view.

## Return Value

A view that fixes this view at its ideal size in the dimensions specified by `horizontal` and `vertical`.

## Discussion

This function behaves like [fixedSize()](fixedSize.zh-Hans.md), except with `fixedSize(horizontal:vertical:)` the fixing of the axes can be optionally specified in one or both dimensions. For example, if you horizontally fix a text view before wrapping it in the frame view, you’re telling the text view to maintain its ideal *width*. The view calculates this to be the space needed to represent the entire string.

```swift
Text("A single line of text, too long to fit in a box.")
    .fixedSize(horizontal: true, vertical: false)
    .frame(width: 200, height: 200)
    .border(Color.gray)
```

This can result in the view exceeding the parent’s bounds, which may or may not be the effect you want.



## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

