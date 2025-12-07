---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubview/sizeThatFits(_:)
抓取时间： 2025-12-01T00:43:12Z
---

# sizeThatFits(_:)

**实例方法**

询问子视图的大小。

## 声明

```swift
func sizeThatFits(_ proposal: ProposedViewSize) -> CGSize
```

## 参数

- **proposal**：建议的子视图大小。在 SwiftUI 中，视图可以选择自己的大小，但也可以考虑父视图的建议大小。

## 返回值

子视图根据其容器视图的建议为自己选择的大小。

## 讨论

使用本方法可以方便地获取[width](../ViewDimensions/width.zh-Hans.md) 和[height](../ViewDimensions/height.zh-Hans.md) 属性，这些属性是由[ViewDimensions](../ViewDimensions.zh-Hans.md) 方法返回的[dimensions(in:)](dimensions_in.zh-Hans.md) 实例的，并作为[doc://com.apple.documentation/documentation/CoreFoundation/CGSize] 实例报告。

## 获取子视图特征

- **dimensions(in:)**：询问子视图的尺寸和对齐方式。
- **spacing**：子视图的首选间距值。
- **priority**：子视图的布局优先级。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubview/sizeThatFits(_:)
crawled: 2025-12-01T00:43:12Z
---

# sizeThatFits(_:)

**Instance Method**

Asks the subview for its size.

## Declaration

```swift
func sizeThatFits(_ proposal: ProposedViewSize) -> CGSize
```

## Parameters

- **proposal**: A proposed size for the subview. In SwiftUI, views choose their own size, but can take a size proposal from their parent view into account when doing so.

## Return Value

The size that the subview chooses for itself, given the proposal from its container view.

## Discussion

Use this method as a convenience to get the [width](../ViewDimensions/width.zh-Hans.md) and [height](../ViewDimensions/height.zh-Hans.md) properties of the [ViewDimensions](../ViewDimensions.zh-Hans.md) instance returned by the [dimensions(in:)](dimensions_in.zh-Hans.md) method, reported as a [doc://com.apple.documentation/documentation/CoreFoundation/CGSize] instance.

## Getting subview characteristics

- **dimensions(in:)**: Asks the subview for its dimensions and alignment guides.
- **spacing**: The subviews’s preferred spacing values.
- **priority**: The layout priority of the subview.

