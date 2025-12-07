--- 来源：https://developer.apple.com/documentation/SwiftUI/View/webViewScrollPosition(_:)

抓取时间：2025-11-30T21:11:30Z

---

# webViewScrollPosition(_:)

**实例方法**

将滚动位置绑定到 Web 视图。

## 声明

```swift
nonisolated func webViewScrollPosition(_ position: Binding<ScrollPosition>) -> some View

```

## 讨论

## 显示 Web 内容

- **WebView**：用于显示 Web 内容的视图。

- **WebPage**：用于控制和管理交互式 Web 内容行为的对象。

- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。

- **webViewContentBackground(_:)**：指定网页自然背景色在此视图中的可见性。

- **webViewContextMenu(menu:)**：向 WebView 添加基于项目的上下文菜单，替换默认的上下文菜单项集。

- **webViewElementFullscreenBehavior(_:)**：确定 WebView 是否可以全屏显示内容。

- **webViewLinkPreviews(_:)**：确定点击链接时是否显示链接目标位置的预览。

- **webViewMagnificationGestures(_:)**：确定放大手势是否改变视图的放大倍数。

- **webViewOnScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。

- **webViewScrollInputBehavior(_:for:)**：启用或禁用使用特定输入时 WebView 中的滚动功能。

- **webViewTextSelection(_:)**：决定是否允许用户选择或以其他方式与文本进行交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/webViewScrollPosition(_:)
crawled: 2025-11-30T21:11:30Z
---

# webViewScrollPosition(_:)

**Instance Method**

Associates a binding to a scroll position with the web view.

## Declaration

```swift
nonisolated func webViewScrollPosition(_ position: Binding<ScrollPosition>) -> some View

```

## Discussion



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
- **webViewScrollInputBehavior(_:for:)**: Enables or disables scrolling in web views when using particular inputs.
- **webViewTextSelection(_:)**: Determines whether to allow people to select or otherwise interact with text.

