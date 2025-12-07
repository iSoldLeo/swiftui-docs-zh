--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollIndicators(_:axes:)

抓取时间：2025-12-02T17:40:37Z

---

# scrollIndicators(_:axes:)

**实例方法**

设置此视图中滚动指示器的可见性。

## 声明

```swift
nonisolated func scrollIndicators(_ visibility: ScrollIndicatorVisibility, axes: Axis.Set = [.vertical, .horizontal]) -> some View

```

## 参数

- **visibility**：要应用于可滚动视图的可见性。

- **axes**：应用此可见性的可滚动视图的轴。

## 返回值

具有指定滚动指示器可见性的视图。

## 讨论

使用此修饰符可以隐藏或显示视图（例如 [ScrollView](../ScrollView.zh-Hans.md)、[List](../List.zh-Hans.md) 或 [TextEditor](../TextEditor.zh-Hans.md)）中可滚动内容的滚动指示器。此修饰符会将首选可见性应用于视图层次结构中的任何可滚动内容。

```swift
ScrollView {
    VStack(alignment: .leading) {
        ForEach(0..<100) {
            Text("Row \($0)")
        }
    }
}
.scrollIndicators(.hidden)
```

使用 [hidden](../ScrollIndicatorVisibility/hidden.zh-Hans.md) 值表示您希望视图在给定轴上始终不显示滚动指示器。如果您希望视图显示滚动指示器，请使用 [visible](../ScrollIndicatorVisibility/visible.zh-Hans.md)。根据平台约定，可见的滚动指示器可能仅在滚动时显示。传递 [automatic](../ScrollIndicatorVisibility/automatic.zh-Hans.md) 可允许视图自行决定是否显示其指示器。

## 显示滚动指示器

- **scrollIndicatorsFlash(onAppear:)**：在可滚动视图出现时闪烁其滚动指示器。

- **scrollIndicatorsFlash(trigger:)**：当值发生变化时，闪烁可滚动视图的滚动指示器。

- **horizontalScrollIndicatorVisibility**：应用于任何水平可滚动内容的滚动指示器的可见性。

- **verticalScrollIndicatorVisibility**：应用于任何垂直可滚动内容的滚动指示器的可见性。

- **ScrollIndicatorVisibility**：UI 元素的滚动指示器的可见性。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollIndicators(_:axes:)
crawled: 2025-12-02T17:40:37Z
---

# scrollIndicators(_:axes:)

**Instance Method**

Sets the visibility of scroll indicators within this view.

## Declaration

```swift
nonisolated func scrollIndicators(_ visibility: ScrollIndicatorVisibility, axes: Axis.Set = [.vertical, .horizontal]) -> some View

```

## Parameters

- **visibility**: The visibility to apply to scrollable views.
- **axes**: The axes of scrollable views that the visibility applies to.

## Return Value

A view with the specified scroll indicator visibility.

## Discussion

Use this modifier to hide or show scroll indicators on scrollable content in views like a [ScrollView](../ScrollView.zh-Hans.md), [List](../List.zh-Hans.md), or [TextEditor](../TextEditor.zh-Hans.md). This modifier applies the preferred visibility to any scrollable content within a view hierarchy.

```swift
ScrollView {
    VStack(alignment: .leading) {
        ForEach(0..<100) {
            Text("Row \($0)")
        }
    }
}
.scrollIndicators(.hidden)
```

Use the [hidden](../ScrollIndicatorVisibility/hidden.zh-Hans.md) value to indicate that you prefer that views never show scroll indicators along a given axis. Use [visible](../ScrollIndicatorVisibility/visible.zh-Hans.md) when you prefer that views show scroll indicators. Depending on platform conventions, visible scroll indicators might only appear while scrolling. Pass [automatic](../ScrollIndicatorVisibility/automatic.zh-Hans.md) to allow views to decide whether or not to show their indicators.

## Showing scroll indicators

- **scrollIndicatorsFlash(onAppear:)**: Flashes the scroll indicators of a scrollable view when it appears.
- **scrollIndicatorsFlash(trigger:)**: Flashes the scroll indicators of scrollable views when a value changes.
- **horizontalScrollIndicatorVisibility**: The visibility to apply to scroll indicators of any horizontally scrollable content.
- **verticalScrollIndicatorVisibility**: The visiblity to apply to scroll indicators of any vertically scrollable content.
- **ScrollIndicatorVisibility**: The visibility of scroll indicators of a UI element.

