---
来源： https://developer.apple.com/documentation/swiftui/nshostingcontroller/safearearegions
抓取时间： 2025-12-04T13:40:42Z
---

# 安全区域

**实例属性**

此视图控制器添加到其视图中的安全区域。

## 声明

```swift
@MainActor @preconcurrency var safeAreaRegions: SafeAreaRegions { get set }
```

## 讨论

默认值为 `SafeAreaRegions.all`。

## 配置控制器

- **sizeThatFits(in:)**：计算并返回最适合当前视图的尺寸。
- **preferredContentSize**：计算并返回当前视图最合适的尺寸。
- **sizingOptions**：托管控制器视图如何根据 SwiftUI 内容的大小创建和更新约束的选项。
- **sceneBridgingOptions**：窗口的哪些方面将由该控制器的托管视图管理的选项。


---
source: https://developer.apple.com/documentation/swiftui/nshostingcontroller/safearearegions
crawled: 2025-12-04T13:40:42Z
---

# safeAreaRegions

**Instance Property**

The safe area regions that this view controller adds to its view.

## Declaration

```swift
@MainActor @preconcurrency var safeAreaRegions: SafeAreaRegions { get set }
```

## Discussion

The default value is `SafeAreaRegions.all`.

## Configuring the controller

- **sizeThatFits(in:)**: Calculates and returns the most appropriate size for the current view.
- **preferredContentSize**
- **sizingOptions**: The options for how the hosting controller’s view creates and updates constraints based on the size of its SwiftUI content.
- **sceneBridgingOptions**: The options for which aspects of the window will be managed by this controller’s hosting view.

