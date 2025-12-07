--- 来源：https://developer.apple.com/documentation/SwiftUI/View/layoutPriority(_:)

抓取时间：2025-11-30T21:23:45Z

---

# layoutPriority(_:)

**实例方法**

设置父布局向子布局分配空间的优先级。

## 声明

```swift
nonisolated func layoutPriority(_ value: Double) -> some View

```

## 参数

- **value**：父布局向子布局分配空间的优先级。

## 说明

视图通常具有默认优先级 `0`，这会导致空间平均分配给所有同级视图。提高视图的布局优先级，可以使优先级较高的视图在组缩小时稍后缩小，在组拉伸时更快地拉伸。

```swift
HStack {
    Text("This is a moderately long string.")
        .font(.largeTitle)
        .border(Color.gray)

    Spacer()

    Text("This is a higher priority string.")
        .font(.largeTitle)
        .layoutPriority(1)
        .border(Color.gray)
}
```

在上面的示例中，第一个 [Text](../Text.zh-Hans.md) 元素的默认优先级为 `0`，由于第二个 [Text](../Text.zh-Hans.md) 元素的优先级更高，即使它们的所有其他属性（字体、字号和字符数）都相同，其视图也会大幅缩小。

父布局会将分配给父视图的所有空间（减去所有低优先级子视图所需的最小空间）分配给优先级最高的子视图。

## 影响视图大小

- **frame(width:height:alignment:)**：将此视图放置在指定大小的不可见框架内。

- **frame(depth:alignment:)**：将此视图放置在指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图放置在具有指定大小约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图定位在一个具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图定位在一个相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在一个相对于最近容器大小的不可见框架内。

- **containerRelativeFrame(_:count:span:spacing:alignment:)**：将此视图定位在一个相对于最近容器大小的不可见框架内。

- **fixedSize()**：将此视图固定在其理想大小。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想大小。


---
source: https://developer.apple.com/documentation/SwiftUI/View/layoutPriority(_:)
crawled: 2025-11-30T21:23:45Z
---

# layoutPriority(_:)

**Instance Method**

Sets the priority by which a parent layout should apportion space to this child.

## Declaration

```swift
nonisolated func layoutPriority(_ value: Double) -> some View

```

## Parameters

- **value**: The priority by which a parent layout apportions space to the child.

## Discussion

Views typically have a default priority of `0` which causes space to be apportioned evenly to all sibling views. Raising a view’s layout priority encourages the higher priority view to shrink later when the group is shrunk and stretch sooner when the group is stretched.

```swift
HStack {
    Text("This is a moderately long string.")
        .font(.largeTitle)
        .border(Color.gray)

    Spacer()

    Text("This is a higher priority string.")
        .font(.largeTitle)
        .layoutPriority(1)
        .border(Color.gray)
}
```

In the example above, the first [Text](../Text.zh-Hans.md) element has the default priority `0` which causes its view to shrink dramatically due to the higher priority of the second [Text](../Text.zh-Hans.md) element, even though all of their other attributes (font, font size and character count) are the same.



A parent layout offers the child views with the highest layout priority all the space offered to the parent minus the minimum space required for all its lower-priority children.

## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:count:span:spacing:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.

