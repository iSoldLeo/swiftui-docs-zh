---
来源： https://developer.apple.com/documentation/swiftui/uihostingcontroller/safearearegions
抓取时间： 2025-12-04T13:47:03Z
---

# 安全区域

**实例属性**

此视图控制器添加到其视图中的安全区域。

## 声明

```swift
@MainActor @preconcurrency var safeAreaRegions: SafeAreaRegions { get set }
```

## 讨论

使用安全区域的一个合适例子是，在托管您知道永远不会受安全区域影响的内容（如自定义可滚动容器）时。禁用安全区域可将其从 SwiftUI 布局系统中完全删除。

默认值为 `SafeAreaRegions.all`。

## 管理大小

- **sizingOptions**：托管控制器如何跟踪其 SwiftUI 内容大小变化的选项。
- **preferredContentSizeDidChange(forChildContentContainer:)**：托管控制器如何跟踪其 SwiftUI 内容大小变化的选项。
- **sizeThatFits(in:)**：计算并返回最适合当前视图的大小。


---
source: https://developer.apple.com/documentation/swiftui/uihostingcontroller/safearearegions
crawled: 2025-12-04T13:47:03Z
---

# safeAreaRegions

**Instance Property**

The safe area regions that this view controller adds to its view.

## Declaration

```swift
@MainActor @preconcurrency var safeAreaRegions: SafeAreaRegions { get set }
```

## Discussion

An example of when this is appropriate to use is when hosting content that you know should never be affected by the safe area, such as a custom scrollable container. Disabling a safe area region omits it from the SwiftUI layout system altogether.

The default value is `SafeAreaRegions.all`.

## Managing the size

- **sizingOptions**: The options for how the hosting controller tracks changes to the size of its SwiftUI content.
- **preferredContentSizeDidChange(forChildContentContainer:)**
- **sizeThatFits(in:)**: Calculates and returns the most appropriate size for the current view.

