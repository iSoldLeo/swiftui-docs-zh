--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scenePadding(_:)

抓取时间：2025-11-30T21:23:36Z

---

# scenePadding(_:)

**实例方法**

根据当前场景，为该视图的指定边缘添加合适的内边距。

## 声明

```swift
nonisolated func scenePadding(_ edges: Edge.Set = .all) -> some View

```

## 参数

- **edges**：要添加内边距的视图边缘集合。

## 返回值

一个在指定边缘添加了场景合适内边距的视图。

## 说明

使用此方法可以为视图添加场景合适的内边距。指定一个来自 [Set](../Edge/Set.zh-Hans.md) 的单个边缘值，或者指定一个描述需要填充边缘的 [doc://com.apple.documentation/documentation/Swift/OptionSet]。

在 macOS 中，使用场景填充可在窗口根视图周围生成推荐的间距。在 watchOS 中，使用场景填充可将用户界面元素与顶级元素（例如导航视图的标题）对齐。例如，比较 watchOS 中 [NavigationView](../NavigationView.zh-Hans.md) 内不同填充方式对文本视图的影响：

```swift
VStack(alignment: .leading, spacing: 10) {
    Text("Scene padding")
        .scenePadding(.horizontal)
        .border(.red) // Border added for reference.
    Text("Regular padding")
        .padding(.horizontal)
        .border(.green)
    Text("Text with no padding")
        .border(.blue)
    Button("Button") { }
}
.navigationTitle("Hello World")
```

使用场景填充的文本会自动与标题对齐，而使用默认填充或不使用填充的文本则不会：

watchOS 中的场景填充还可以确保您的内容避开 Apple Watch Series 7 等设备的曲面边缘。在其他平台上，场景填充产生的默认填充与 [padding(_:_:)](padding.zh-Hans.md) 修饰符的默认填充相同。

## 为视图添加内边距

- **padding(_:)**：为该视图的每条边添加不同的内边距。

- **padding(_:_:)**：为该视图的特定边添加相等的内边距。

- **padding3D(_:)**：使用您指定的边内边距为该视图添加内边距。

- **padding3D(_:_:)**：使用您指定的边内边距为该视图添加内边距。

- **scenePadding(_:edges:)**：使用适合当前场景的内边距，为该视图的指定边添加指定类型的内边距。

- **ScenePadding**：用于将视图与其包含场景分隔开的内边距。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scenePadding(_:)
crawled: 2025-11-30T21:23:36Z
---

# scenePadding(_:)

**Instance Method**

Adds padding to the specified edges of this view using an amount that’s appropriate for the current scene.

## Declaration

```swift
nonisolated func scenePadding(_ edges: Edge.Set = .all) -> some View

```

## Parameters

- **edges**: The set of edges along which to pad this view.

## Return Value

A view that’s padded on specified edges by a scene-appropriate amount.

## Discussion

Use this modifier to add a scene-appropriate amount of padding to a view. Specify either a single edge value from [Set](../Edge/Set.zh-Hans.md), or an [doc://com.apple.documentation/documentation/Swift/OptionSet] that describes the edges to pad.

In macOS, use scene padding to produce the recommended spacing around the root view of a window. In watchOS, use scene padding to align elements of your user interface with top level elements, like the title of a navigation view. For example, compare the effects of different kinds of padding on text views presented inside a [NavigationView](../NavigationView.zh-Hans.md) in watchOS:

```swift
VStack(alignment: .leading, spacing: 10) {
    Text("Scene padding")
        .scenePadding(.horizontal)
        .border(.red) // Border added for reference.
    Text("Regular padding")
        .padding(.horizontal)
        .border(.green)
    Text("Text with no padding")
        .border(.blue)
    Button("Button") { }
}
.navigationTitle("Hello World")
```

The text with scene padding automatically aligns with the title, unlike the text that uses the default padding or the text without padding:



Scene padding in watchOS also ensures that your content avoids the curved edges of a device like Apple Watch Series 7. In other platforms, scene padding produces the same default padding that you get from the [padding(_:_:)](padding.zh-Hans.md) modifier.



## Adding padding around a view

- **padding(_:)**: Adds a different padding amount to each edge of this view.
- **padding(_:_:)**: Adds an equal padding amount to specific edges of this view.
- **padding3D(_:)**: Pads this view using the edge insets you specify.
- **padding3D(_:_:)**: Pads this view using the edge insets you specify.
- **scenePadding(_:edges:)**: Adds a specified kind of padding to the specified edges of this view using an amount that’s appropriate for the current scene.
- **ScenePadding**: The padding used to space a view from its containing scene.

