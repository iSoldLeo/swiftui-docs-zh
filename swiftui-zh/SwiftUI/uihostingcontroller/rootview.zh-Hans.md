---
来源： https://developer.apple.com/documentation/swiftui/uihostingcontroller/rootview
抓取时间： 2025-12-04T13:46:54Z
---

# 根视图

**实例属性**

该视图控制器管理的 SwiftUI 视图层次结构的根视图。

## 声明

```swift
@MainActor @preconcurrency var rootView: Content { get set }
```

## 响应与视图相关的事件

- **loadView()**
- **viewWillAppear(_:)**：通知视图控制器其视图即将添加到视图层次结构中。
- **viewDidAppear(_:)**：通知视图控制器其视图已被添加到视图层次结构中。
- **viewWillDisappear(_:)**：通知视图控制器其视图将从视图层次结构中移除。
- **viewDidDisappear(_:)**：通知视图控制器其视图将从视图层次结构中移除。
- **willMove(toParent:)**：通知视图控制器将其视图从视图层次结构中移除。
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**


---
source: https://developer.apple.com/documentation/swiftui/uihostingcontroller/rootview
crawled: 2025-12-04T13:46:54Z
---

# rootView

**Instance Property**

The root view of the SwiftUI view hierarchy managed by this view controller.

## Declaration

```swift
@MainActor @preconcurrency var rootView: Content { get set }
```

## Responding to view-related events

- **loadView()**
- **viewWillAppear(_:)**: Notifies the view controller that its view is about to be added to a view hierarchy.
- **viewDidAppear(_:)**: Notifies the view controller that its view has been added to a view hierarchy.
- **viewWillDisappear(_:)**: Notifies the view controller that its view will be removed from a view hierarchy.
- **viewDidDisappear(_:)**
- **willMove(toParent:)**
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**

