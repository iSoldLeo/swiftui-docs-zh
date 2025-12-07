---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewVisibility/automatic
抓取时间：2025-12-02T20:58:39Z
---

# 自动

**类型属性**

使用当前设备的默认前导列可见性。

## 声明

```swift
static var automatic: NavigationSplitViewVisibility { get }
```

## 讨论

此计算属性返回三种具体情况之一：[detailOnly](detailOnly.zh-Hans.md)、[doubleColumn](doubleColumn.zh-Hans.md) 或 [all](all.zh-Hans.md)。

## 获取可见度

- **all**：显示三栏导航拆分视图的所有栏。
- **doubleColumn**：显示三栏导航拆分视图的内容栏和详细区域，或显示两栏导航拆分视图的侧边栏和详细区域。
- **detailOnly**：隐藏三栏导航拆分视图的前两栏，以便只显示详细区域。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewVisibility/automatic
crawled: 2025-12-02T20:58:39Z
---

# automatic

**Type Property**

Use the default leading column visibility for the current device.

## Declaration

```swift
static var automatic: NavigationSplitViewVisibility { get }
```

## Discussion

This computed property returns one of the three concrete cases: [detailOnly](detailOnly.zh-Hans.md), [doubleColumn](doubleColumn.zh-Hans.md), or [all](all.zh-Hans.md).

## Getting visibilities

- **all**: Show all the columns of a three-column navigation split view.
- **doubleColumn**: Show the content column and detail area of a three-column navigation split view, or the sidebar column and detail area of a two-column navigation split view.
- **detailOnly**: Hide the leading two columns of a three-column navigation split view, so that just the detail area shows.

