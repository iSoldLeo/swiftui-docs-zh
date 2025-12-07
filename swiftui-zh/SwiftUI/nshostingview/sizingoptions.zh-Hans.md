--- 来源：https://developer.apple.com/documentation/swiftui/nshostingview/sizingoptions

抓取时间：2025-12-04T13:45:13Z

---

# sizingOptions

**实例属性**

用于设置宿主视图如何根据其 SwiftUI 内容的大小创建和更新约束。

## 声明

```swift
@MainActor @preconcurrency var sizingOptions: NSHostingSizingOptions { get set }
```

## 讨论

NSHostingView 可以创建基于其 SwiftUI 视图内容的最小、最大和理想（内容大小）约束。这些约束仅在包含窗口中使用自动布局约束时才会创建。

如果将 NSHostingView 设置为 `NSWindow` 的 `contentView`，它还会根据 SwiftUI 内容的最小和最大尺寸更新窗口的 `contentMinSize` 和 `contentMaxSize`。

`sizingOptions` 的默认值为 `.standardBounds`（包含 `minSize`、`intrinsicContentSize` 和 `maxSize`），但可以显式设置为特定值来控制此行为。例如，将值设置为 `.minSize` 将仅创建维护 SwiftUI 内容最小尺寸所需的约束，而将值设置为 `[]` 则不会创建任何约束。

如果某个用例可以对 `NSHostingView` 相对于其显示内容的大小做出假设（例如，它始终显示在固定框架中），则将其设置为选项较少的值可以提高性能，因为它减少了需要执行的布局测量次数。如果 `NSHostingView` 的 `frame` 小于或大于显示其 SwiftUI 内容所需的尺寸，则内容将在该框架内居中显示。

## 修改框架矩形

- **intrinsicContentSize**

- **setFrameSize(_:)**

- **firstBaselineOffsetFromTop**

- **lastBaselineOffsetFromBottom**

- **firstTextLineCenter**


---
source: https://developer.apple.com/documentation/swiftui/nshostingview/sizingoptions
crawled: 2025-12-04T13:45:13Z
---

# sizingOptions

**Instance Property**

The options for how the hosting view creates and updates constraints based on the size of its SwiftUI content.

## Declaration

```swift
@MainActor @preconcurrency var sizingOptions: NSHostingSizingOptions { get set }
```

## Discussion

NSHostingView can create minimum, maximum, and ideal (content size) constraints that are derived from its SwiftUI view content. These constraints are only created when Auto Layout constraints are otherwise being used in the containing window.

If the NSHostingView is set as the `contentView` of an `NSWindow`, it will also update the window’s `contentMinSize` and `contentMaxSize` based on the minimum and maximum size of its SwiftUI content.

`sizingOptions` defaults to `.standardBounds` (which includes `minSize`, `intrinsicContentSize`, and `maxSize`), but can be set to an explicit value to control this behavior. For instance, setting a value of `.minSize` will only create the constraints necessary to maintain the minimum size of the SwiftUI content, or setting a value of `[]` will create no constraints at all.

If a use case can make assumptions about the size of the `NSHostingView` relative to its displayed content, such as the always being displayed in a fixed frame, setting this to a value with fewer options can improve performance as it reduces the amount of layout measurements that need to be performed. If an `NSHostingView` has a `frame` that is smaller or larger than that required to display its SwiftUI content, the content will be centered within that frame.

## Modifying the frame rectangle

- **intrinsicContentSize**
- **setFrameSize(_:)**
- **firstBaselineOffsetFromTop**
- **lastBaselineOffsetFromBottom**
- **firstTextLineCenter**

