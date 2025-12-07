--- 来源：https://developer.apple.com/documentation/swiftui/view/frame(width:height:alignment:)

抓取时间：2025-12-02T17:29:04Z

---

# frame(width:height:alignment:)

**实例方法**

将此视图放置在指定大小的不可见框架内。

## 声明

```swift
nonisolated func frame(width: CGFloat? = nil, height: CGFloat? = nil, alignment: Alignment = .center) -> some View

```

## 参数

- **width**：生成的视图的固定宽度。如果 `width` 为 `nil`，则生成的视图将采用此视图的尺寸行为。

- **height**：生成的视图的固定高度。如果 `height` 为 `nil`，则生成的视图将采用此视图的尺寸行为。

- **alignment**：此视图在生成的框架内的对齐方式。请注意，当框架的大小恰好与此视图的大小匹配时，大多数对齐值不会产生明显的影响。

## 返回值

对于非 `nil` 的参数，返回一个尺寸固定为 `width` 和 `height` 的视图。

## 说明

使用此方法可以指定视图的宽度、高度或两者的固定大小。如果仅指定其中一个尺寸，则生成的视图在另一个尺寸上将采用此视图的尺寸行为。

例如，以下代码在一个固定的 200 x 100 框架中布局一个椭圆。由于形状始终占据布局系统提供的空间，因此第一个椭圆的尺寸为 200x100 点。第二个椭圆布局在一个高度固定的框架中，因此它占据该高度，以及布局系统为其父元素提供的任何宽度。

```swift
VStack {
    Ellipse()
        .fill(Color.purple)
        .frame(width: 200, height: 100)
    Ellipse()
        .fill(Color.blue)
        .frame(height: 100)
}
```

`The alignment` 参数指定此视图在框架内的对齐方式。

```swift
Text("Hello world!")
    .frame(width: 200, height: 30, alignment: .topLeading)
    .border(Color.gray)
```

在上面的示例中，文本位于框架的顶部前角。如果文本的高度超过框架，则其边界可能会超出框架的底部边界。

## 影响视图大小

- **frame(depth:alignment:)**：将此视图定位在具有指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图定位在一个具有指定尺寸约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图定位在一个具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图定位在一个相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在一个相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在一个相对于最近容器大小的不可见框架内。

- **fixedSize()**：将此视图固定在其理想尺寸。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想尺寸。

- **layoutPriority(_:)**：设置父布局向子布局分配空间的优先级。


---
source: https://developer.apple.com/documentation/swiftui/view/frame(width:height:alignment:)
crawled: 2025-12-02T17:29:04Z
---

# frame(width:height:alignment:)

**Instance Method**

Positions this view within an invisible frame with the specified size.

## Declaration

```swift
nonisolated func frame(width: CGFloat? = nil, height: CGFloat? = nil, alignment: Alignment = .center) -> some View

```

## Parameters

- **width**: A fixed width for the resulting view. If `width` is `nil`, the resulting view assumes this view’s sizing behavior.
- **height**: A fixed height for the resulting view. If `height` is `nil`, the resulting view assumes this view’s sizing behavior.
- **alignment**: The alignment of this view inside the resulting frame. Note that most alignment values have no apparent effect when the size of the frame happens to match that of this view.

## Return Value

A view with fixed dimensions of `width` and `height`, for the parameters that are non-`nil`.

## Discussion

Use this method to specify a fixed size for a view’s width, height, or both. If you only specify one of the dimensions, the resulting view assumes this view’s sizing behavior in the other dimension.

For example, the following code lays out an ellipse in a fixed 200 by 100 frame. Because a shape always occupies the space offered to it by the layout system, the first ellipse is 200x100 points. The second ellipse is laid out in a frame with only a fixed height, so it occupies that height, and whatever width the layout system offers to its parent.

```swift
VStack {
    Ellipse()
        .fill(Color.purple)
        .frame(width: 200, height: 100)
    Ellipse()
        .fill(Color.blue)
        .frame(height: 100)
}
```



`The alignment` parameter specifies this view’s alignment within the frame.

```swift
Text("Hello world!")
    .frame(width: 200, height: 30, alignment: .topLeading)
    .border(Color.gray)
```

In the example above, the text is positioned at the top, leading corner of the frame. If the text is taller than the frame, its bounds may extend beyond the bottom of the frame’s bounds.



## Influencing a view’s size

- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

