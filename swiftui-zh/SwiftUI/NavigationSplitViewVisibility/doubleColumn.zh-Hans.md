---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewVisibility/doubleColumn
抓取时间： 2025-12-02T20:58:41Z
---

# doubleColumn

**类型属性**

显示三栏导航拆分视图的内容栏和详细区域，或显示两栏导航拆分视图的边栏栏和详细区域。

## 声明

```swift
static var doubleColumn: NavigationSplitViewVisibility { get }
```

## 讨论

对于双栏导航分割视图，`doubleColumn` 等同于 `all`。

## 获取可见性

- **automatic**：使用当前设备的默认前导列可见性。
- **all**：显示三列导航分割视图的所有列。
- **detailOnly**：隐藏三栏导航拆分视图的前两栏，以便只显示详细信息区域。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewVisibility/doubleColumn
crawled: 2025-12-02T20:58:41Z
---

# doubleColumn

**Type Property**

Show the content column and detail area of a three-column navigation split view, or the sidebar column and detail area of a two-column navigation split view.

## Declaration

```swift
static var doubleColumn: NavigationSplitViewVisibility { get }
```

## Discussion

For a two-column navigation split view, `doubleColumn` is equivalent to `all`.

## Getting visibilities

- **automatic**: Use the default leading column visibility for the current device.
- **all**: Show all the columns of a three-column navigation split view.
- **detailOnly**: Hide the leading two columns of a three-column navigation split view, so that just the detail area shows.

