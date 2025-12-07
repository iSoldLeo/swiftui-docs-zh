--- 来源：https://developer.apple.com/documentation/SwiftUI/View/webViewMagnificationGestures(_:)

抓取时间：2025-11-30T21:11:27Z

---

# webViewMagnificationGestures(_:)

**实例方法**

确定放大手势是否会改变视图的放大倍数。

## 声明

```swift
nonisolated func webViewMagnificationGestures(_ value: WebView.MagnificationGesturesBehavior) -> some View

```

## 显示网页内容

- **WebView**：显示网页内容的视图。

- **WebPage**：控制和管理交互式网页内容行为的对象。

- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。

- **webViewContentBackground(_:)**：指定网页自然背景色在此视图中的可见性。

- **webViewContextMenu(menu:)**：向 WebView 添加基于项目的上下文菜单，替换默认的上下文菜单项集。

- **webViewElementFullscreenBehavior(_:)**：确定 WebView 是否可以全屏显示内容。

- **webViewLinkPreviews(_:)**：确定点击链接时是否显示链接目标页面的预览。

- **webViewOnScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。

- **webViewScrollInputBehavior(_:for:)**：启用或禁用使用特定输入时 WebView 中的滚动功能。

- **webViewScrollPosition(_:)**：将滚动位置绑定到 WebView。

- **webViewTextSelection(_:)**：决定是否允许用户选择或以其他方式与文本进行交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/webViewMagnificationGestures(_:)
crawled: 2025-11-30T21:11:27Z
---

# webViewMagnificationGestures(_:)

**Instance Method**

Determines whether magnify gestures change the view’s magnification.

## Declaration

```swift
nonisolated func webViewMagnificationGestures(_ value: WebView.MagnificationGesturesBehavior) -> some View

```

## Displaying web content

- **WebView**: A view that displays some web content.
- **WebPage**: An object that controls and manages the behavior of interactive web content.
- **webViewBackForwardNavigationGestures(_:)**: Determines whether horizontal swipe gestures trigger backward and forward page navigation.
- **webViewContentBackground(_:)**: Specifies the visibility of the webpage’s natural background color within this view.
- **webViewContextMenu(menu:)**: Adds an item-based context menu to a WebView, replacing the default set of context menu items.
- **webViewElementFullscreenBehavior(_:)**: Determines whether a web view can display content full screen.
- **webViewLinkPreviews(_:)**: Determines whether pressing a link displays a preview of the destination for the link.
- **webViewOnScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **webViewScrollInputBehavior(_:for:)**: Enables or disables scrolling in web views when using particular inputs.
- **webViewScrollPosition(_:)**: Associates a binding to a scroll position with the web view.
- **webViewTextSelection(_:)**: Determines whether to allow people to select or otherwise interact with text.

