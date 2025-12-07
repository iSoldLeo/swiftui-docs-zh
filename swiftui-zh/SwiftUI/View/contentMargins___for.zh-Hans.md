--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contentMargins(_:for:)

抓取时间：2025-12-02T17:38:54Z

---

# contentMargins(_:for:)

**实例方法**

配置指定位置的内容边距。

## 声明

```swift
nonisolated func contentMargins(_ length: CGFloat, for placement: ContentMarginPlacement = .automatic) -> some View

```

## 参数

- **length**：所有边缘要添加的边距量。

- **placement**：边距的添加位置。

## 说明

使用此方法可以自定义不同类型视图的内容边距。例如，您可以使用此方法自定义可滚动视图（如 [ScrollView](../ScrollView.zh-Hans.md)）的边距。在以下示例中，滚动视图的内容会自动内缩，内缩距离为安全区域加上前后边缘各 20 个点。

```swift
ScrollView(.horizontal) {
    // ...
}
.contentMargins(.horizontal, 20.0)
```

您可以提供 [ContentMarginPlacement](../ContentMarginPlacement.zh-Hans.md) 来定位视图的特定部分进行自定义。例如，提供 [scrollContent](../ContentMarginPlacement/scrollContent.zh-Hans.md) 来内缩 [TextEditor](../TextEditor.zh-Hans.md) 的内容，而不会影响其滚动指示器的内缩。

```swift
TextEditor(text: $text)
    .contentMargins(.horizontal, 20.0, for: .scrollContent)
```

类似地，您可以分别自定义滚动指示器和滚动内容的内缩。当应用可能会裁剪指示器的自定义裁剪形状时，请考虑这样做。

```swift
ScrollView {
    // ...
}
.clipShape(.rect(cornerRadius: 20.0))
.contentMargins(10.0, for: .scrollIndicators)
```

应用多个 contentMargins 修改器时，位置相同的修改器会覆盖视图层次结构中位置更高的修改器。

## 设置边距

- **contentMargins(_:_:for:)**：配置指定位置的内容边距。

- **ContentMarginPlacement**：边距的放置位置。


---
source: https://developer.apple.com/documentation/SwiftUI/View/contentMargins(_:for:)
crawled: 2025-12-02T17:38:54Z
---

# contentMargins(_:for:)

**Instance Method**

Configures the content margin for a provided placement.

## Declaration

```swift
nonisolated func contentMargins(_ length: CGFloat, for placement: ContentMarginPlacement = .automatic) -> some View

```

## Parameters

- **length**: The amount of margins to add on all edges.
- **placement**: Where the margins should be added.

## Discussion

Use this modifier to customize the content margins of different kinds of views. For example, you can use this modifier to customize the margins of scrollable views like [ScrollView](../ScrollView.zh-Hans.md). In the following example, the scroll view will automatically inset its content by the safe area plus an additional 20 points on the leading and trailing edge.

```swift
ScrollView(.horizontal) {
    // ...
}
.contentMargins(.horizontal, 20.0)
```

You can provide a [ContentMarginPlacement](../ContentMarginPlacement.zh-Hans.md) to target specific parts of a view to customize. For example, provide a [scrollContent](../ContentMarginPlacement/scrollContent.zh-Hans.md) placement to inset the content of a [TextEditor](../TextEditor.zh-Hans.md) without affecting the insets of its scroll indicators.

```swift
TextEditor(text: $text)
    .contentMargins(.horizontal, 20.0, for: .scrollContent)
```

Similarly, you can customize the insets of scroll indicators separately from scroll content. Consider doing this when applying a custom clip shape that may clip the indicators.

```swift
ScrollView {
    // ...
}
.clipShape(.rect(cornerRadius: 20.0))
.contentMargins(10.0, for: .scrollIndicators)
```

When applying multiple contentMargins modifiers, modifiers with the same placement will override modifiers higher up in the view hierarchy.

## Setting margins

- **contentMargins(_:_:for:)**: Configures the content margin for a provided placement.
- **ContentMarginPlacement**: The placement of margins.

