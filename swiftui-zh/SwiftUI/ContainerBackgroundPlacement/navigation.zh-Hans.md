---
来源： https://developer.apple.com/documentation/SwiftUI/ContainerBackgroundPlacement/navigation
抓取时间： 2025-12-03T06:36:15Z
---

# 导航

**类型属性**

[NavigationStack](../NavigationStack.zh-Hans.md)或[NavigationSplitView](../NavigationSplitView.zh-Hans.md)内的背景位置。

## 声明

```swift
static let navigation: ContainerBackgroundPlacement
```

## 讨论

对于导航分割视图中的半透明背景，将此位置与 [navigationSplitView](navigationSplitView.zh-Hans.md)结合使用。

```swift
NavigationSplitView {
     … sidebar …
    .containerBackground(.thinMaterial, for: .navigation)
    .containerBackground(Color.green, for: .navigationSplitView)
} detail: {
    // … detail …
    .containerBackground(.thickMaterial, for: .navigation)
}
```

## 获取位置

- **tabView**：[TabView](../TabView.zh-Hans.md)内的背景位置。
- **widget**：部件的容器背景位置。


---
source: https://developer.apple.com/documentation/SwiftUI/ContainerBackgroundPlacement/navigation
crawled: 2025-12-03T06:36:15Z
---

# navigation

**Type Property**

A background placement inside a [NavigationStack](../NavigationStack.zh-Hans.md) or [NavigationSplitView](../NavigationSplitView.zh-Hans.md).

## Declaration

```swift
static let navigation: ContainerBackgroundPlacement
```

## Discussion

For translucent backgrounds in a navigation split view, combine this placement with [navigationSplitView](navigationSplitView.zh-Hans.md).

```swift
NavigationSplitView {
     … sidebar …
    .containerBackground(.thinMaterial, for: .navigation)
    .containerBackground(Color.green, for: .navigationSplitView)
} detail: {
    // … detail …
    .containerBackground(.thickMaterial, for: .navigation)
}
```

## Getting placements

- **tabView**: A background placement inside a [TabView](../TabView.zh-Hans.md).
- **widget**: The container background placement for a widget.

