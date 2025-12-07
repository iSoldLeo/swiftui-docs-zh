--- 来源：https://developer.apple.com/documentation/SwiftUI/View/webViewOnScrollGeometryChange(for:of:action:)

抓取时间：2025-11-30T21:11:28Z

---

# webViewOnScrollGeometryChange(for:of:action:)

**实例方法**

添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。

## 声明

```swift
nonisolated func webViewOnScrollGeometryChange<T>(for type: T.Type, of transform: @escaping (ScrollGeometry) -> T, action: @escaping (T, T) -> Void) -> some View where T : Hashable

```

## 参数

- **type**：由 [ScrollGeometry](../ScrollGeometry.zh-Hans.md) 转换而来的值的类型。

- **transform**：将 [ScrollGeometry](../ScrollGeometry.zh-Hans.md) 转换为您指定类型的闭包。

- **action**：当转换后的数据发生变化时要运行的闭包。

## 返回值

当 Web 视图滚动几何体的相关部分发生变化时，会调用该操作的视图。

## 讨论

## 显示 Web 内容

- **WebView**：显示某些 Web 内容的视图。

- **WebPage**：控制和管理交互式 Web 内容行为的对象。

- **webViewBackForwardNavigationGestures(_:)**：确定水平滑动是否触发页面前后导航。

- **webViewContentBackground(_:)**：指定此视图中网页自然背景颜色的可见性。

- **webViewContextMenu(menu:)**：向 WebView 添加基于项目的上下文菜单，替换默认的上下文菜单项集。

- **webViewElementFullscreenBehavior(_:)**：确定网页视图是否可以全屏显示内容。

- **webViewLinkPreviews(_:)**：确定点击链接时是否显示链接指向的目标页面的预览。

- **webViewMagnificationGestures(_:)**：确定放大手势是否改变视图的放大倍数。

- **webViewScrollInputBehavior(_:for:)**：启用或禁用使用特定输入方式时网页视图的滚动功能。

- **webViewScrollPosition(_:)**：将网页视图的滚动位置绑定到相应的按键。

- **webViewTextSelection(_:)**：确定是否允许用户选择文本或以其他方式与文本进行交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/webViewOnScrollGeometryChange(for:of:action:)
crawled: 2025-11-30T21:11:28Z
---

# webViewOnScrollGeometryChange(for:of:action:)

**Instance Method**

Adds an action to be performed when a value, created from a scroll geometry, changes.

## Declaration

```swift
nonisolated func webViewOnScrollGeometryChange<T>(for type: T.Type, of transform: @escaping (ScrollGeometry) -> T, action: @escaping (T, T) -> Void) -> some View where T : Hashable

```

## Parameters

- **type**: The type of value transformed from a [ScrollGeometry](../ScrollGeometry.zh-Hans.md).
- **transform**: A closure that transforms a [ScrollGeometry](../ScrollGeometry.zh-Hans.md) to your type.
- **action**: A closure to run when the transformed data changes.

## Return Value

A view that invokes the action when the relevant part of a web view’s scroll geometry changes.

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
- **webViewScrollInputBehavior(_:for:)**: Enables or disables scrolling in web views when using particular inputs.
- **webViewScrollPosition(_:)**: Associates a binding to a scroll position with the web view.
- **webViewTextSelection(_:)**: Determines whether to allow people to select or otherwise interact with text.

