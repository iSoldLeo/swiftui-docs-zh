--- 来源：https://developer.apple.com/documentation/SwiftUI/View/containerRelativeFrame(_:count:span:spacing:alignment:)

抓取时间：2025-12-02T17:38:38Z

---

# containerRelativeFrame(_:count:span:spacing:alignment:)

**实例方法**

将此视图定位在一个不可见的框架内，框架的大小相对于最近的容器。

## 声明

```swift
nonisolated func containerRelativeFrame(_ axes: Axis.Set, count: Int, span: Int = 1, spacing: CGFloat, alignment: Alignment = .center) -> some View

```

## 讨论

使用 [containerRelativeFrame(_:alignment:)](containerRelativeFrame___alignment.zh-Hans.md) 修饰符可以指定视图的宽度、高度或两者的大小，该大小取决于最近的容器的大小。不同的对象可以表示“容器”，包括：

- 在 iPadOS 或 macOS 上显示视图的窗口，或 iOS 设备上的屏幕。

- NavigationSplitView 的一列

- NavigationStack

- TabView 的一个标签页

- 可滚动视图，例如 ScrollView 或 List

此修饰符提供的尺寸是容器（例如上面列出的容器）的尺寸，减去可能应用于该容器的任何安全区域内边距。

以下示例将使每个紫色矩形在 iOS 上占据整个屏幕：

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 0.0) {
        ForEach(items) { item in
            Rectangle()
                .fill(.purple)
                .containerRelativeFrame([.horizontal, .vertical])
        }
    }
}
```

使用此修饰符调整视图大小，以便在容器中显示多个视图。使用此修饰符时，count 指的是容器在特定轴上的长度应分成的总行数或列数。span 指的是修改后的视图实际应占据的行数或列数。因此，元素的大小可以这样描述：

```swift
let availableWidth = (containerWidth - (spacing * (count - 1)))
let columnWidth = (availableWidth / count)
let itemWidth = (columnWidth * span) + ((span - 1) * spacing)
```

以下示例仅使用水平轴上最接近的容器尺寸，允许使用 [aspectRatio(_:contentMode:)](aspectRatio___contentMode.zh-Hans.md) 修饰符确定垂直轴。 ```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 10.0) {
        ForEach(items) { item in
            Rectangle()
                .fill(.purple)
                .aspectRatio(3.0 / 2.0, contentMode: .fit)
                .containerRelativeFrame(
                    .horizontal, count: 4, span: 3, spacing: 10.0)
        }
    }
}
.safeAreaPadding(.horizontal, 20.0)
```

使用 [containerRelativeFrame(_:alignment:_:)](containerRelativeFrame___alignment.zh-Hans.md) 修饰符，您可以应用自定义逻辑来调整视图附近容器的大小。以下示例会将容器框架的宽度除以 3，并将该值用作紫色矩形的宽度。

```swift
Rectangle()
    .fill(.purple)
    .aspectRatio(1.0, contentMode: .fill)
    .containerRelativeFrame(
        .horizontal, alignment: .topLeading
    ) { length, axis in
        if axis == .vertical {
            return length / 3.0
        } else {
            return length / 5.0
        }
    }
```

## 影响视图的大小

- **frame(width:height:alignment:)**：将此视图放置在指定大小的不可见框架内。

- **frame(depth:alignment:)**：将此视图放置在指定深度的不可见框架内。

- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**：将此视图放置在具有指定大小约束的不可见框架内。

- **frame(minDepth:idealDepth:maxDepth:alignment:)**：将此视图放置在具有指定深度约束的不可见框架内。

- **containerRelativeFrame(_:alignment:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **containerRelativeFrame(_:alignment:_:)**：将此视图定位在一个不可见的框架内，框架大小相对于最近的容器。

- **fixedSize()**：将此视图固定在理想大小。

- **fixedSize(horizontal:vertical:)**：将此视图固定在指定尺寸的理想大小。

- **layoutPriority(_:)**：设置父布局分配给此子布局空间的优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/View/containerRelativeFrame(_:count:span:spacing:alignment:)
crawled: 2025-12-02T17:38:38Z
---

# containerRelativeFrame(_:count:span:spacing:alignment:)

**Instance Method**

Positions this view within an invisible frame with a size relative to the nearest container.

## Declaration

```swift
nonisolated func containerRelativeFrame(_ axes: Axis.Set, count: Int, span: Int = 1, spacing: CGFloat, alignment: Alignment = .center) -> some View

```

## Discussion

Use the [containerRelativeFrame(_:alignment:)](containerRelativeFrame___alignment.zh-Hans.md) modifier to specify a size for a view’s width, height, or both that is dependent on the size of the nearest container. Different things can represent a “container” including:

- The window presenting a view on iPadOS or macOS, or the screen of a device on iOS.
- A column of a NavigationSplitView
- A NavigationStack
- A tab of a TabView
- A scrollable view like ScrollView or List

The size provided to this modifier is the size of a container like the ones listed above subtracting any safe area insets that might be applied to that container.

The following example will have each purple rectangle occupy the full size of the screen on iOS:

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 0.0) {
        ForEach(items) { item in
            Rectangle()
                .fill(.purple)
                .containerRelativeFrame([.horizontal, .vertical])
        }
    }
}
```

Use this modifier to size a view such that multiple views will be visible in the container. When using this modifier, the count refers to the total number of rows or columns that the length of the container size in a particular axis should be divided into. The span refers to the number of rows or columns that the modified view should actually occupy. Thus the size of the element can be described like so:

```swift
let availableWidth = (containerWidth - (spacing * (count - 1)))
let columnWidth = (availableWidth / count)
let itemWidth = (columnWidth * span) + ((span - 1) * spacing)
```

The following example only uses the nearest container size in the horizontal axis, allowing the vertical axis to be determined using the [aspectRatio(_:contentMode:)](aspectRatio___contentMode.zh-Hans.md) modifier.

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 10.0) {
        ForEach(items) { item in
            Rectangle()
                .fill(.purple)
                .aspectRatio(3.0 / 2.0, contentMode: .fit)
                .containerRelativeFrame(
                    .horizontal, count: 4, span: 3, spacing: 10.0)
        }
    }
}
.safeAreaPadding(.horizontal, 20.0)
```

Use the [containerRelativeFrame(_:alignment:_:)](containerRelativeFrame___alignment.zh-Hans.md) modifier to apply your own custom logic to adjust the size of the nearest container for your view. The following example will result in the container frame’s width being divided by 3 and using that value as the width of the purple rectangle.

```swift
Rectangle()
    .fill(.purple)
    .aspectRatio(1.0, contentMode: .fill)
    .containerRelativeFrame(
        .horizontal, alignment: .topLeading
    ) { length, axis in
        if axis == .vertical {
            return length / 3.0
        } else {
            return length / 5.0
        }
    }
```

## Influencing a view’s size

- **frame(width:height:alignment:)**: Positions this view within an invisible frame with the specified size.
- **frame(depth:alignment:)**: Positions this view within an invisible frame with the specified depth.
- **frame(minWidth:idealWidth:maxWidth:minHeight:idealHeight:maxHeight:alignment:)**: Positions this view within an invisible frame having the specified size constraints.
- **frame(minDepth:idealDepth:maxDepth:alignment:)**: Positions this view within an invisible frame having the specified depth constraints.
- **containerRelativeFrame(_:alignment:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **containerRelativeFrame(_:alignment:_:)**: Positions this view within an invisible frame with a size relative to the nearest container.
- **fixedSize()**: Fixes this view at its ideal size.
- **fixedSize(horizontal:vertical:)**: Fixes this view at its ideal size in the specified dimensions.
- **layoutPriority(_:)**: Sets the priority by which a parent layout should apportion space to this child.

