--- 来源：https://developer.apple.com/documentation/SwiftUI/View/webViewContextMenu(menu:)

抓取时间：2025-11-30T21:11:25Z

---

# webViewContextMenu(menu:)

**实例方法**

向 WebView 添加基于项的上下文菜单，替换默认的上下文菜单项集。

## 声明

```swift
nonisolated func webViewContextMenu(@ViewBuilder menu: @escaping @MainActor (WebView.ActivatedElementInfo) -> some View) -> some View

```

## 参数

- **menu**：生成菜单的闭包。闭包的唯一参数描述了被操作的网页元素类型。

## 返回值

一个可以显示基于项的上下文菜单的视图。

## 显示网页内容

- **WebView**：一个显示网页内容的视图。

- **WebPage**：用于控制和管理交互式网页内容行为的对象。

- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。

- **webViewContentBackground(_:)**：指定网页自然背景色在此视图中的可见性。

- **webViewElementFullscreenBehavior(_:)**：确定网页视图是否可以全屏显示内容。

- **webViewLinkPreviews(_:)**：确定点击链接是否显示链接目标位置的预览。

- **webViewMagnificationGestures(_:)**：确定放大手势是否改变视图的缩放比例。

- **webViewOnScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。

- **webViewScrollInputBehavior(_:for:)**：启用或禁用使用特定输入框时网页视图的滚动功能。

- **webViewScrollPosition(_:)**：将网页视图的滚动位置绑定到相应的控件。

- **webViewTextSelection(_:)**：确定是否允许用户选择文本或以其他方式与文本进行交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/webViewContextMenu(menu:)
crawled: 2025-11-30T21:11:25Z
---

# webViewContextMenu(menu:)

**Instance Method**

Adds an item-based context menu to a WebView, replacing the default set of context menu items.

## Declaration

```swift
nonisolated func webViewContextMenu(@ViewBuilder menu: @escaping @MainActor (WebView.ActivatedElementInfo) -> some View) -> some View

```

## Parameters

- **menu**: A closure that produces the menu. The single parameter to the closure describes the type of webpage element that was acted upon.

## Return Value

A view that can display an item-based context menu.

## Displaying web content

- **WebView**: A view that displays some web content.
- **WebPage**: An object that controls and manages the behavior of interactive web content.
- **webViewBackForwardNavigationGestures(_:)**: Determines whether horizontal swipe gestures trigger backward and forward page navigation.
- **webViewContentBackground(_:)**: Specifies the visibility of the webpage’s natural background color within this view.
- **webViewElementFullscreenBehavior(_:)**: Determines whether a web view can display content full screen.
- **webViewLinkPreviews(_:)**: Determines whether pressing a link displays a preview of the destination for the link.
- **webViewMagnificationGestures(_:)**: Determines whether magnify gestures change the view’s magnification.
- **webViewOnScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **webViewScrollInputBehavior(_:for:)**: Enables or disables scrolling in web views when using particular inputs.
- **webViewScrollPosition(_:)**: Associates a binding to a scroll position with the web view.
- **webViewTextSelection(_:)**: Determines whether to allow people to select or otherwise interact with text.

