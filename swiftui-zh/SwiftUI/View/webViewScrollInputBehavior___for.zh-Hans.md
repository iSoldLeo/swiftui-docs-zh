--- 来源：https://developer.apple.com/documentation/SwiftUI/View/webViewScrollInputBehavior(_:for:)

抓取时间：2025-11-30T21:11:29Z

---

# webViewScrollInputBehavior(_:for:)

**实例方法**

启用或禁用特定输入框在网页视图中的滚动功能。

## 声明

```swift
nonisolated func webViewScrollInputBehavior(_ behavior: ScrollInputBehavior, for input: ScrollInputKind) -> some View

```

## 参数

- **behavior**：是否启用或禁用此输入框的滚动功能。

- **input**：要启用或禁用滚动功能的输入框。

## 返回值

一个已配置网页视图滚动输入行为的视图。

## 显示网页内容

- **WebView**：用于显示网页内容的视图。

- **WebPage**：用于控制和管理交互式网页内容行为的对象。

- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。

- **webViewContentBackground(_:)**：指定网页自然背景色在此视图中的可见性。

- **webViewContextMenu(menu:)**：向 WebView 添加基于项目的上下文菜单，替换默认的上下文菜单项集。

- **webViewElementFullscreenBehavior(_:)**：确定 WebView 是否可以全屏显示内容。

- **webViewLinkPreviews(_:)**：确定点击链接是否显示链接目标页面的预览。

- **webViewMagnificationGestures(_:)**：确定放大手势是否改变视图的放大倍数。

- **webViewOnScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。

- **webViewScrollPosition(_:)**：将滚动位置绑定到 Web 视图。

- **webViewTextSelection(_:)**：确定是否允许用户选择文本或以其他方式与文本交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/webViewScrollInputBehavior(_:for:)
crawled: 2025-11-30T21:11:29Z
---

# webViewScrollInputBehavior(_:for:)

**Instance Method**

Enables or disables scrolling in web views when using particular inputs.

## Declaration

```swift
nonisolated func webViewScrollInputBehavior(_ behavior: ScrollInputBehavior, for input: ScrollInputKind) -> some View

```

## Parameters

- **behavior**: Whether scrolling should be enabled or disabled for this input.
- **input**: The input for which to enable or disable scrolling.

## Return Value

A view with the configured scroll input behavior for web views.

## Displaying web content

- **WebView**: A view that displays some web content.
- **WebPage**: An object that controls and manages the behavior of interactive web content.
- **webViewBackForwardNavigationGestures(_:)**: Determines whether horizontal swipe gestures trigger backward and forward page navigation.
- **webViewContentBackground(_:)**: Specifies the visibility of the webpage’s natural background color within this view.
- **webViewContextMenu(menu:)**: Adds an item-based context menu to a WebView, replacing the default set of context menu items.
- **webViewElementFullscreenBehavior(_:)**: Determines whether a web view can display content full screen.
- **webViewLinkPreviews(_:)**: Determines whether pressing a link displays a preview of the destination for the link.
- **webViewMagnificationGestures(_:)**: Determines whether magnify gestures change the view’s magnification.
- **webViewOnScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **webViewScrollPosition(_:)**: Associates a binding to a scroll position with the web view.
- **webViewTextSelection(_:)**: Determines whether to allow people to select or otherwise interact with text.

