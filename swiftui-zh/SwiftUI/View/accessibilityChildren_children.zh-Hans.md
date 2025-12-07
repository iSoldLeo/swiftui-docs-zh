--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityChildren(children:)

抓取时间：2025-12-02T16:49:01Z

---

# accessibilityChildren(children:)

**实例方法**

将现有辅助功能元素的子元素替换为一个或多个新的合成辅助功能元素。

## 声明

```swift
nonisolated func accessibilityChildren<V>(@ViewBuilder children: () -> V) -> some View where V : View

```

## 参数

- **children**：一个 [ViewBuilder](../ViewBuilder.zh-Hans.md)，表示框架用于生成辅助功能元素的替换子视图。

## 说明

使用此修饰符可将现有元素的子元素替换为您提供的一个或多个新的合成辅助功能元素。这允许将合成的、非视觉的辅助功能元素设置为视觉辅助功能元素的子元素。

SwiftUI 会在需要时隐式创建辅助功能容器。如果辅助功能元素已存在，框架会将其转换为辅助功能容器。

在下面的示例中，[Canvas](../Canvas.zh-Hans.md) 显示了一个垂直条形图，该图本身没有任何辅助功能元素。您可以通过添加 [accessibilityChildren(children:)](accessibilityChildren_children.zh-Hans.md) 修饰符，并添加辅助功能元素代表画布中绘制的每个条形值对应的视图，来使该视图具有辅助功能：

```swift
var body: some View {
    Canvas { context, size in
        // Draw Graph
        for data in dataSet {
            let path = Path(
                roundedRect: CGRect(
                    x: (size.width / CGFloat(dataSet.count))
                    * CGFloat(data.week),
                    y: 0,
                    width: size.width / CGFloat(dataSet.count),
                    height: CGFloat(data.lines),
                cornerRadius: 5)
            context.fill(path, with: .color(.blue))
        }
        // Draw Axis and Labels
        ...
    }
    .accessibilityLabel("Lines of Code per Week")
    .accessibilityChildren {
        HStack {
            ForEach(dataSet) { data in
                RoundedRectangle(cornerRadius: 5)
                    .accessibilityLabel("Week \(data.week)")
                    .accessibilityValue("\(data.lines) lines")
            }
        }
    }
}
```

SwiftUI 会隐藏您使用 `children` 参数提供的所有视图，然后框架会使用这些视图来生成辅助功能元素。

## 创建辅助功能元素

- **accessibilityElement(children:)**：创建一个新的辅助功能元素，或修改现有辅助功能元素的 [AccessibilityChildBehavior](../AccessibilityChildBehavior.zh-Hans.md)。

- **accessibilityRepresentation(representation:)**：将此视图的一个或多个辅助功能元素替换为新的辅助功能元素。

- **AccessibilityChildBehavior**：定义新父元素的子元素的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityChildren(children:)
crawled: 2025-12-02T16:49:01Z
---

# accessibilityChildren(children:)

**Instance Method**

Replaces the existing accessibility element’s children with one or more new synthetic accessibility elements.

## Declaration

```swift
nonisolated func accessibilityChildren<V>(@ViewBuilder children: () -> V) -> some View where V : View

```

## Parameters

- **children**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that represents the replacement child views the framework uses to generate accessibility elements.

## Discussion

Use this modifier to replace an existing element’s children with one or more new synthetic accessibility elements you provide. This allows for synthetic, non-visual accessibility elements to be set as children of a visual accessibility element.

SwiftUI creates an accessibility container implicitly when needed. If an accessibility element already exists, the framework converts it into an accessibility container.

In the  example below, a [Canvas](../Canvas.zh-Hans.md) displays a graph of vertical bars that don’t have any inherent accessibility elements. You make the view accessible by adding the [accessibilityChildren(children:)](accessibilityChildren_children.zh-Hans.md) modifier with views whose accessibility elements represent the values of each bar drawn in the canvas:

```swift
var body: some View {
    Canvas { context, size in
        // Draw Graph
        for data in dataSet {
            let path = Path(
                roundedRect: CGRect(
                    x: (size.width / CGFloat(dataSet.count))
                    * CGFloat(data.week),
                    y: 0,
                    width: size.width / CGFloat(dataSet.count),
                    height: CGFloat(data.lines),
                cornerRadius: 5)
            context.fill(path, with: .color(.blue))
        }
        // Draw Axis and Labels
        ...
    }
    .accessibilityLabel("Lines of Code per Week")
    .accessibilityChildren {
        HStack {
            ForEach(dataSet) { data in
                RoundedRectangle(cornerRadius: 5)
                    .accessibilityLabel("Week \(data.week)")
                    .accessibilityValue("\(data.lines) lines")
            }
        }
    }
}
```

SwiftUI hides any views that you provide with the `children` parameter, then the framework uses the views to generate the accessibility elements.

## Creating accessible elements

- **accessibilityElement(children:)**: Creates a new accessibility element, or modifies the [AccessibilityChildBehavior](../AccessibilityChildBehavior.zh-Hans.md) of the existing accessibility element.
- **accessibilityRepresentation(representation:)**: Replaces one or more accessibility elements for this view with new accessibility elements.
- **AccessibilityChildBehavior**: Defines the behavior for the child elements of the new parent element.

