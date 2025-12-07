---
来源：https://developer.apple.com/documentation/SwiftUI/UIHostingController/target(forAction:withSender:)
抓取时间：2025-12-01T11:48:13Z
---

# target(forAction:withSender:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

- [ target(forAction:withSender:) ](/documentation/SwiftUI/UIHostingController/target(forAction:withSender:))

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

- target(forAction:withSender:)

实例方法# target(forAction:withSender:)

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
@MainActor @preconcurrency
override dynamic func target(
    forAction action: Selector,
    withSender sender: Any?
) -> Any?
```

## [See Also](/documentation/SwiftUI/UIHostingController/target(forAction:withSender:)#see-also)

### [响应与视图相关的事件](/documentation/SwiftUI/UIHostingController/target(forAction:withSender:)#响应与视图相关的事件)

[`func loadView()`](/documentation/swiftui/uihostingcontroller/loadview())[`func viewWillAppear(Bool)`](/documentation/swiftui/uihostingcontroller/viewwillappear(_:))通知视图控制器其视图即将被添加到视图层次结构中。[`func viewDidAppear(Bool)`](/documentation/swiftui/uihostingcontroller/viewdidappear(_:))通知视图控制器其视图已被添加到视图层次结构中。[`func viewWillDisappear(Bool)`](/documentation/swiftui/uihostingcontroller/viewwilldisappear(_:))通知视图控制器其视图将从视图层次结构中移除。[`func viewDidDisappear(Bool)`](/documentation/swiftui/uihostingcontroller/viewdiddisappear(_:))[`func willMove(toParent: UIViewController?)`](/documentation/swiftui/uihostingcontroller/willmove(toparent:))[`func didMove(toParent: UIViewController?)`](/documentation/swiftui/uihostingcontroller/didmove(toparent:))[`func viewWillTransition(to: CGSize, with: any UIViewControllerTransitionCoordinator)`](/documentation/swiftui/uihostingcontroller/viewwilltransition(to:with:))[`func viewWillLayoutSubviews()`](/documentation/swiftui/uihostingcontroller/viewwilllayoutsubviews())[`var rootView: Content`](/documentation/swiftui/uihostingcontroller/rootview)The由该视图控制器管理的 SwiftUI 视图层次结构的根视图。

---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingController/target(forAction:withSender:)
crawled: 2025-12-01T11:48:13Z
---

# target(forAction:withSender:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

- [ target(forAction:withSender:) ](/documentation/SwiftUI/UIHostingController/target(forAction:withSender:))

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

-  target(forAction:withSender:) 

Instance Method# target(forAction:withSender:)

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
@MainActor @preconcurrency
override dynamic func target(
    forAction action: Selector,
    withSender sender: Any?
) -> Any?
```

## [See Also](/documentation/SwiftUI/UIHostingController/target(forAction:withSender:)#see-also)

### [Responding to view-related events](/documentation/SwiftUI/UIHostingController/target(forAction:withSender:)#Responding-to-view-related-events)

[`func loadView()`](/documentation/swiftui/uihostingcontroller/loadview())[`func viewWillAppear(Bool)`](/documentation/swiftui/uihostingcontroller/viewwillappear(_:))Notifies the view controller that its view is about to be added to a view hierarchy.[`func viewDidAppear(Bool)`](/documentation/swiftui/uihostingcontroller/viewdidappear(_:))Notifies the view controller that its view has been added to a view hierarchy.[`func viewWillDisappear(Bool)`](/documentation/swiftui/uihostingcontroller/viewwilldisappear(_:))Notifies the view controller that its view will be removed from a view hierarchy.[`func viewDidDisappear(Bool)`](/documentation/swiftui/uihostingcontroller/viewdiddisappear(_:))[`func willMove(toParent: UIViewController?)`](/documentation/swiftui/uihostingcontroller/willmove(toparent:))[`func didMove(toParent: UIViewController?)`](/documentation/swiftui/uihostingcontroller/didmove(toparent:))[`func viewWillTransition(to: CGSize, with: any UIViewControllerTransitionCoordinator)`](/documentation/swiftui/uihostingcontroller/viewwilltransition(to:with:))[`func viewWillLayoutSubviews()`](/documentation/swiftui/uihostingcontroller/viewwilllayoutsubviews())[`var rootView: Content`](/documentation/swiftui/uihostingcontroller/rootview)The root view of the SwiftUI view hierarchy managed by this view controller.