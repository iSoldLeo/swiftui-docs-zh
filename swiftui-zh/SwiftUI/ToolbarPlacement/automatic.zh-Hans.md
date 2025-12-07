---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarPlacement/automatic
抓取时间： 2025-12-03T06:05:02Z
---

# 自动

**类型属性**

主工具栏。

## 声明

```swift
static var automatic: ToolbarPlacement { get }
```

## 讨论

根据上下文，这可能指 iOS 或 watchOS 上应用程序的导航栏、tvOS 上应用程序的标签栏或 macOS 上应用程序的窗口工具栏/窗口标题栏。

## 获取位置

- **accessoryBar(id:)**：创建独特的附件栏位置。
- **bottomBar**：应用程序的底部工具栏。
- **bottomOrnament**：应用程序的底部工具栏：应用程序的底部装饰。
- **navigationBar**：应用程序的导航栏。
- **tabBar**：应用程序的导航栏：应用程序的标签栏。
- **windowToolbar**：应用程序的标签栏：包含窗口的工具栏的位置，有时也称为标题栏。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarPlacement/automatic
crawled: 2025-12-03T06:05:02Z
---

# automatic

**Type Property**

The primary toolbar.

## Declaration

```swift
static var automatic: ToolbarPlacement { get }
```

## Discussion

Depending on the context, this may refer to the navigation bar of an app on iOS, or watchOS, the tab bar of an app on tvOS, or the window toolbar / window titlebar of an app on macOS.

## Getting placements

- **accessoryBar(id:)**: Creates a unique accessory bar placement.
- **bottomBar**: The bottom toolbar of an app.
- **bottomOrnament**: The bottom ornament of an app.
- **navigationBar**: The navigation bar of an app.
- **tabBar**: The tab bar of an app.
- **windowToolbar**: The placement for the containing window’s toolbar, sometimes referred to as the titlebar.

