---
来源： https://developer.apple.com/documentation/swiftui/nshostingcontroller/sizingoptions
抓取时间： 2025-12-04T13:40:41Z
---

# sizingOptions

**实例属性**

托管控制器视图如何根据 SwiftUI 内容大小创建和更新约束的选项。

## 声明

```swift
@MainActor @preconcurrency var sizingOptions: NSHostingSizingOptions { get set }
```

## 讨论

NSHostingController 可以创建最小、最大和理想（内容大小）约束，这些约束源自 SwiftUI 视图内容。只有在包含窗口中使用自动布局约束时，才会创建这些约束。

如果 NSHostingController 被设置为`contentViewController` 的`NSWindow`，它还将根据其 SwiftUI 内容的最小和最大尺寸更新窗口的`contentMinSize` 和`contentMaxSize`。

`sizingOptions`默认为`.standardBounds`（其中包括`minSize`、`intrinsicContentSize`和`maxSize`），但也可以设置一个明确的值来控制此行为。例如，如果将`.minSize` 设置为 `.minSize`，则只会创建保持 SwiftUI 内容最小尺寸所需的限制，如果将`[]` 设置为 `.minSize`，则根本不会创建任何限制。

如果用例可以假设`NSHostingController` 相对于其显示内容的大小，例如总是在固定框架中显示，那么将其设置为一个选项较少的值可以提高性能，因为它减少了需要执行的布局测量量。如果`NSHostingController` 的`frame` 小于或大于显示 SwiftUI 内容所需的`NSHostingController`，则内容将在该框架内居中显示。

## 配置控制器

- **sizeThatFits(in:)**：计算并返回最适合当前视图的尺寸。
- **preferredContentSize**：计算并返回当前视图最合适的尺寸。
- **safeAreaRegions**：该视图控制器添加到其视图中的安全区域。
- **sceneBridgingOptions**：窗口的哪些方面将由该控制器的托管视图管理的选项。


---
source: https://developer.apple.com/documentation/swiftui/nshostingcontroller/sizingoptions
crawled: 2025-12-04T13:40:41Z
---

# sizingOptions

**Instance Property**

The options for how the hosting controller’s view creates and updates constraints based on the size of its SwiftUI content.

## Declaration

```swift
@MainActor @preconcurrency var sizingOptions: NSHostingSizingOptions { get set }
```

## Discussion

NSHostingController can create minimum, maximum, and ideal (content size) constraints that are derived from its SwiftUI view content. These constraints are only created when Auto Layout constraints are otherwise being used in the containing window.

If the NSHostingController is set as the `contentViewController` of an `NSWindow`, it will also update the window’s `contentMinSize` and `contentMaxSize` based on the minimum and maximum size of its SwiftUI content.

`sizingOptions` defaults to `.standardBounds` (which includes `minSize`, `intrinsicContentSize`, and `maxSize`), but can be set to an explicit value to control this behavior. For instance, setting a value of `.minSize` will only create the constraints necessary to maintain the minimum size of the SwiftUI content, or setting a value of `[]` will create no constraints at all.

If a use case can make assumptions about the size of the `NSHostingController` relative to its displayed content, such as the always being displayed in a fixed frame, setting this to a value with fewer options can improve performance as it reduces the amount of layout measurements that need to be performed. If an `NSHostingController` has a `frame` that is smaller or larger than that required to display its SwiftUI content, the content will be centered within that frame.

## Configuring the controller

- **sizeThatFits(in:)**: Calculates and returns the most appropriate size for the current view.
- **preferredContentSize**
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.
- **sceneBridgingOptions**: The options for which aspects of the window will be managed by this controller’s hosting view.

