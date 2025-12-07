---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarPlacement/windowToolbar
抓取时间： 2025-12-03T06:05:07Z
---

# 窗口工具栏

**类型属性**

包含窗口的工具栏的位置，有时也称为标题栏。

## 声明

```swift
static var windowToolbar: ToolbarPlacement { get }
```

## 讨论

使用 [toolbar(_:for:)](../View/toolbar___for.zh-Hans.md) 隐藏时，会隐藏整个窗口工具栏，包括标题和 "交通灯 "窗口控件。要只删除自定义工具栏项目内容，请使用 [automatic](automatic.zh-Hans.md)。

使用 [toolbarBackground(_:for:)](../View/toolbarBackground___for.zh-Hans.md) 隐藏窗口工具栏的背景。

## 获取位置

- **automatic**：主工具栏。
- **accessoryBar(id:)**：创建独特的附件栏位置。
- **bottomBar**：应用程序的底部工具栏。
- **bottomOrnament**：应用程序的底部工具栏：应用程序的底部装饰。
- **navigationBar**：应用程序的导航栏。
- **tabBar**：应用程序的导航栏：应用程序的标签栏。


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarPlacement/windowToolbar
crawled: 2025-12-03T06:05:07Z
---

# windowToolbar

**Type Property**

The placement for the containing window’s toolbar, sometimes referred to as the titlebar.

## Declaration

```swift
static var windowToolbar: ToolbarPlacement { get }
```

## Discussion

When hidden using [toolbar(_:for:)](../View/toolbar___for.zh-Hans.md), this hides the entire window toolbar, including the title and “traffic light” window controls. To remove the custom toolbar item content only, use [automatic](automatic.zh-Hans.md).

Use [toolbarBackground(_:for:)](../View/toolbarBackground___for.zh-Hans.md) to hide the background of the window toolbar.

## Getting placements

- **automatic**: The primary toolbar.
- **accessoryBar(id:)**: Creates a unique accessory bar placement.
- **bottomBar**: The bottom toolbar of an app.
- **bottomOrnament**: The bottom ornament of an app.
- **navigationBar**: The navigation bar of an app.
- **tabBar**: The tab bar of an app.

