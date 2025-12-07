---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/bottomBar
抓取时间： 2025-12-03T06:03:10Z
---

# bottomBar

**类型属性**

将项目置于底部工具栏。

## 声明

```swift
static let bottomBar: ToolbarItemPlacement
```

## 讨论

在 tvOS 上，这只适用于[NavigationSplitView](../NavigationSplitView.zh-Hans.md) 的侧边栏。  在其他地方使用则无效。

## 获取明确的位置

- **topBarLeading**：将项目置于顶栏的前缘。
- **topBarTrailing**：将项目置于顶栏的后缘。
- **bottomOrnament**：将项目置于窗口下方的装饰物中。
- **keyboard**：将项目置于键盘部分。
- **accessoryBar(id:)**：创建独特的附件栏位置。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarItemPlacement/bottomBar
crawled: 2025-12-03T06:03:10Z
---

# bottomBar

**Type Property**

Places the item in the bottom toolbar.

## Declaration

```swift
static let bottomBar: ToolbarItemPlacement
```

## Discussion

On tvOS, this applies only within the sidebar of a [NavigationSplitView](../NavigationSplitView.zh-Hans.md).  It has no effect if used elsewhere.

## Getting explicit placement

- **topBarLeading**: Places the item in the leading edge of the top bar.
- **topBarTrailing**: Places the item in the trailing edge of the top bar.
- **bottomOrnament**: Places the item in an ornament under the window.
- **keyboard**: The item is placed in the keyboard section.
- **accessoryBar(id:)**: Creates a unique accessory bar placement.

