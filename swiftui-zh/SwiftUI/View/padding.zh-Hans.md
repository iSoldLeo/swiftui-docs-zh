--- 来源：https://developer.apple.com/documentation/SwiftUI/View/padding(_:_:)

抓取时间：2025-12-02T17:38:30Z

---

# padding(_:_:)

**实例方法**

为该视图的指定边添加等量的内边距。

## 声明

```swift
nonisolated func padding(_ edges: Edge.Set = .all, _ length: CGFloat? = nil) -> some View

```

## 参数

- **edges**：要为该视图添加内边距的边集。默认值为 [all](../Edge/Set/all.zh-Hans.md)。

- **length**：以点为单位的内边距数值，用于指定边的内边距。如果将值设置为 `nil`，SwiftUI 将使用平台特定的默认内边距数值。此参数的默认值为 `nil`。

## 返回值

在指定边缘添加指定内边距的视图。

## 说明

使用此修饰符可为视图的一个或多个边缘添加指定量的内边距。要指定要添加内边距的边缘，可以指定 [Set](../Edge/Set.zh-Hans.md) 中的单个值，也可以指定包含边缘值的 [doc://com.apple.documentation/documentation/Swift/OptionSet]：

```swift
VStack {
    Text("Text padded by 20 points on the bottom and trailing edges.")
        .padding([.bottom, .trailing], 20)
        .border(.gray)
    Text("Unpadded text for comparison.")
        .border(.yellow)
}
```

应用修饰符的顺序很重要。上面的示例在应用边框之前应用了内边距，以确保边框包含内边距区域：

您可以省略其中一个或两个参数。如果省略 `length`，SwiftUI 将使用默认的内边距量。如果省略 `edges`，SwiftUI 会将内边距应用于所有边缘。省略这两个参数，则会在视图周围添加默认内边距。SwiftUI 会根据平台和显示上下文选择合适的默认内边距。

```swift
VStack {
    Text("Text with default padding.")
        .padding()
        .border(.gray)
    Text("Unpadded text for comparison.")
        .border(.yellow)
}
```

在典型情况下，上述示例在 iOS 中的显示效果如下：

要独立控制每个边缘的内边距，请使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/View/padding(_:)-6pgqq]。要按指定量为视图的所有外边缘添加内边距，请使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/View/padding(_:)-68shk]。

## 为视图添加内边距

- **padding(_:)**：为该视图的每个边缘添加不同的内边距。

- **padding3D(_:)**：使用您指定的边缘内边距为该视图添加内边距。

- **padding3D(_:_:)**：使用您指定的边内边距为该视图添加内边距。

- **scenePadding(_:)**：使用适合当前场景的内边距量，为该视图的指定边添加内边距。

- **scenePadding(_:edges:)**：使用适合当前场景的内边距量，为该视图的指定边添加指定类型的内边距。

- **ScenePadding**：用于将视图与其包含场景分隔开的内边距。


---
source: https://developer.apple.com/documentation/SwiftUI/View/padding(_:_:)
crawled: 2025-12-02T17:38:30Z
---

# padding(_:_:)

**Instance Method**

Adds an equal padding amount to specific edges of this view.

## Declaration

```swift
nonisolated func padding(_ edges: Edge.Set = .all, _ length: CGFloat? = nil) -> some View

```

## Parameters

- **edges**: The set of edges to pad for this view. The default is [all](../Edge/Set/all.zh-Hans.md).
- **length**: An amount, given in points, to pad this view on the specified edges. If you set the value to `nil`, SwiftUI uses a platform-specific default amount. The default value of this parameter is `nil`.

## Return Value

A view that’s padded by the specified amount on the specified edges.

## Discussion

Use this modifier to add a specified amount of padding to one or more edges of the view. Indicate the edges to pad by naming either a single value from [Set](../Edge/Set.zh-Hans.md), or by specifying an [doc://com.apple.documentation/documentation/Swift/OptionSet] that contains edge values:

```swift
VStack {
    Text("Text padded by 20 points on the bottom and trailing edges.")
        .padding([.bottom, .trailing], 20)
        .border(.gray)
    Text("Unpadded text for comparison.")
        .border(.yellow)
}
```

The order in which you apply modifiers matters. The example above applies the padding before applying the border to ensure that the border encompasses the padded region:



You can omit either or both of the parameters. If you omit the `length`, SwiftUI uses a default amount of padding. If you omit the `edges`, SwiftUI applies the padding to all edges. Omit both to add a default padding all the way around a view. SwiftUI chooses a default amount of padding that’s appropriate for the platform and the presentation context.

```swift
VStack {
    Text("Text with default padding.")
        .padding()
        .border(.gray)
    Text("Unpadded text for comparison.")
        .border(.yellow)
}
```

The example above looks like this in iOS under typical conditions:



To control the amount of padding independently for each edge, use [doc://com.apple.SwiftUI/documentation/SwiftUI/View/padding(_:)-6pgqq]. To pad all outside edges of a view by a specified amount, use [doc://com.apple.SwiftUI/documentation/SwiftUI/View/padding(_:)-68shk].

## Adding padding around a view

- **padding(_:)**: Adds a different padding amount to each edge of this view.
- **padding3D(_:)**: Pads this view using the edge insets you specify.
- **padding3D(_:_:)**: Pads this view using the edge insets you specify.
- **scenePadding(_:)**: Adds padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **scenePadding(_:edges:)**: Adds a specified kind of padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **ScenePadding**: The padding used to space a view from its containing scene.

