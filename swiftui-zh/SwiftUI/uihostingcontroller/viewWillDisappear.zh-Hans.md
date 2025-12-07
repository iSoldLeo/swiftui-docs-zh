---
来源： https://developer.apple.com/documentation/swiftui/uihostingcontroller/viewwilldisappear(_:)
抓取时间： 2025-12-04T13:46:14Z
---

# viewWillDisappear(_:)

**实例方法**

通知视图控制器其视图将从视图层次结构中删除。

## 声明

```swift
@MainActor @preconcurrency override dynamic func viewWillDisappear(_ animated: Bool)
```

## 参数

- **animated**：如果 `true`，则使用动画移除视图。

## 讨论

SwiftUI 在从视图层次结构中移除托管控制器的根视图之前会调用此方法。您可以重载此方法来执行与视图消失相关的自定义任务。如果重载此方法，则必须在实现过程中的某个时刻调用 `super`。

## 响应与视图相关的事件

- **loadView()**
- **viewWillAppear(_:)**：通知视图控制器其视图即将添加到视图层次结构中。
- **viewDidAppear(_:)**：通知视图控制器其视图已被添加到视图层次结构中。
- **viewDidDisappear(_:)**：通知视图控制器其视图已添加到视图层次结构中。
- **willMove(toParent:)**：通知视图控制器其视图已添加到视图层次结构中。
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**
- **rootView**：由该视图控制器管理的 SwiftUI 视图层次结构的根视图。


---
source: https://developer.apple.com/documentation/swiftui/uihostingcontroller/viewwilldisappear(_:)
crawled: 2025-12-04T13:46:14Z
---

# viewWillDisappear(_:)

**Instance Method**

Notifies the view controller that its view will be removed from a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency override dynamic func viewWillDisappear(_ animated: Bool)
```

## Parameters

- **animated**: If `true`, the view is being removed using an animation.

## Discussion

SwiftUI calls this method before removing the hosting controller’s root view from the view hierarchy. You can override this method to perform custom tasks associated with the disappearance of the view. If you override this method, you must call `super` at some point in your implementation.

## Responding to view-related events

- **loadView()**
- **viewWillAppear(_:)**: Notifies the view controller that its view is about to be added to a view hierarchy.
- **viewDidAppear(_:)**: Notifies the view controller that its view has been added to a view hierarchy.
- **viewDidDisappear(_:)**
- **willMove(toParent:)**
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**
- **rootView**: The root view of the SwiftUI view hierarchy managed by this view controller.

