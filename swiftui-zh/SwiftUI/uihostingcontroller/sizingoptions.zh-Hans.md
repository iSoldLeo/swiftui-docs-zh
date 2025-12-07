---
来源： https://developer.apple.com/documentation/swiftui/uihostingcontroller/sizingoptions
抓取时间： 2025-12-04T13:47:01Z
---

# sizingOptions

**实例属性**

托管控制器如何跟踪 SwiftUI 内容大小变化的选项。

## 声明

```swift
@MainActor @preconcurrency var sizingOptions: UIHostingControllerSizingOptions { get set }
```

## 讨论

默认值为空集。

## 管理大小

- **preferredContentSizeDidChange(forChildContentContainer:)**
- **sizeThatFits(in:)**：计算并返回最适合当前视图的尺寸。
- **safeAreaRegions**：该视图控制器添加到其视图中的安全区域。


---
source: https://developer.apple.com/documentation/swiftui/uihostingcontroller/sizingoptions
crawled: 2025-12-04T13:47:01Z
---

# sizingOptions

**Instance Property**

The options for how the hosting controller tracks changes to the size of its SwiftUI content.

## Declaration

```swift
@MainActor @preconcurrency var sizingOptions: UIHostingControllerSizingOptions { get set }
```

## Discussion

The default value is the empty set.

## Managing the size

- **preferredContentSizeDidChange(forChildContentContainer:)**
- **sizeThatFits(in:)**: Calculates and returns the most appropriate size for the current view.
- **safeAreaRegions**: The safe area regions that this view controller adds to its view.

