--- 来源：https://developer.apple.com/documentation/SwiftUI/View/webViewContentBackground(_:)

抓取时间：2025-12-02T17:26:17Z

---

# webViewContentBackground(_:)

**实例方法**

指定网页自然背景色在此视图中的可见性。

## 声明

```swift
nonisolated func webViewContentBackground(_ visibility: Visibility) -> some View

```

## 参数

- **visibility**：用于背景的可见性。

## 返回值

具有指定内容背景可见性的视图。

## 说明

默认情况下，WebView 是不透明的，并使用页面的自然背景色作为其背景色。如果您不想使用默认行为，而是希望使用 SwiftUI 提供自定义背景，请使用此修饰符。

## 显示网页内容

- **WebView**：用于显示网页内容的视图。

- **WebPage**：用于控制和管理交互式网页内容行为的对象。

- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。

- **webViewContextMenu(menu:)**：向 WebView 添加基于项目的上下文菜单，替换默认的上下文菜单项集。

- **webViewElementFullscreenBehavior(_:)**：确定 WebView 是否可以全屏显示内容。

- **webViewLinkPreviews(_:)**：确定点击链接时是否显示链接目标页面的预览。

- **webViewMagnificationGestures(_:)**：确定放大手势是否改变视图的缩放比例。

- **webViewOnScrollGeometryChange(for:of:action:)**：当由滚动几何体创建的值发生变化时，添加要执行的操作。

- **webViewScrollInputBehavior(_:for:)**：启用或禁用使用特定输入时 Web 视图中的滚动。

- **webViewScrollPosition(_:)**：将滚动位置绑定到 Web 视图。

- **webViewTextSelection(_:)**：确定是否允许用户选择文本或以其他方式与文本交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/webViewContentBackground(_:)
crawled: 2025-12-02T17:26:17Z
---

# webViewContentBackground(_:)

**Instance Method**

Specifies the visibility of the webpage’s natural background color within this view.

## Declaration

```swift
nonisolated func webViewContentBackground(_ visibility: Visibility) -> some View

```

## Parameters

- **visibility**: The visibility to use for the background.

## Return Value

A view with the specified content background visibility.

## Discussion

By default, WebViews are opaque, and use the page’s natural background color as their background color. Use this modifier if you would like to not use this behavior and instead provide a custom background using SwiftUI.

## Displaying web content

- **WebView**: A view that displays some web content.
- **WebPage**: An object that controls and manages the behavior of interactive web content.
- **webViewBackForwardNavigationGestures(_:)**: Determines whether horizontal swipe gestures trigger backward and forward page navigation.
- **webViewContextMenu(menu:)**: Adds an item-based context menu to a WebView, replacing the default set of context menu items.
- **webViewElementFullscreenBehavior(_:)**: Determines whether a web view can display content full screen.
- **webViewLinkPreviews(_:)**: Determines whether pressing a link displays a preview of the destination for the link.
- **webViewMagnificationGestures(_:)**: Determines whether magnify gestures change the view’s magnification.
- **webViewOnScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **webViewScrollInputBehavior(_:for:)**: Enables or disables scrolling in web views when using particular inputs.
- **webViewScrollPosition(_:)**: Associates a binding to a scroll position with the web view.
- **webViewTextSelection(_:)**: Determines whether to allow people to select or otherwise interact with text.

