---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingController/viewDidAppear(_:)
抓取时间： 2025-12-03T06:58:25Z
---

# viewDidAppear(_:)

**实例方法**

通知视图控制器其视图已被添加到视图层次结构中。

## 声明

```swift
@MainActor @preconcurrency override dynamic func viewDidAppear(_ animated: Bool)
```

## 参数

- **animated**：如果 `true`，则使用动画添加视图。

## 讨论

SwiftUI 在将托管控制器的根视图添加到视图层次结构后会调用此方法。您可以重载此方法来执行与视图外观相关的自定义任务。如果重载此方法，则必须在实现过程中的某个时刻调用 `super`。

## 响应与视图相关的事件

- **loadView()**
- **viewWillAppear(_:)**：通知视图控制器其视图即将添加到视图层次结构中。
- **viewWillDisappear(_:)**：通知视图控制器其视图将从视图层次结构中移除。
- **viewDidDisappear(_:)**：通知视图控制器其视图将从视图层次结构中删除。
- **willMove(toParent:)**：通知视图控制器将其视图从视图层次结构中移除。
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**
- **rootView**：由该视图控制器管理的 SwiftUI 视图层次结构的根视图。


---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingController/viewDidAppear(_:)
crawled: 2025-12-03T06:58:25Z
---

# viewDidAppear(_:)

**Instance Method**

Notifies the view controller that its view has been added to a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency override dynamic func viewDidAppear(_ animated: Bool)
```

## Parameters

- **animated**: If `true`, the view is being added using an animation.

## Discussion

SwiftUI calls this method after adding the hosting controller’s root view to the view hierarchy. You can override this method to perform custom tasks associated with the appearance of the view. If you override this method, you must call `super` at some point in your implementation.

## Responding to view-related events

- **loadView()**
- **viewWillAppear(_:)**: Notifies the view controller that its view is about to be added to a view hierarchy.
- **viewWillDisappear(_:)**: Notifies the view controller that its view will be removed from a view hierarchy.
- **viewDidDisappear(_:)**
- **willMove(toParent:)**
- **didMove(toParent:)**
- **viewWillTransition(to:with:)**
- **viewWillLayoutSubviews()**
- **target(forAction:withSender:)**
- **rootView**: The root view of the SwiftUI view hierarchy managed by this view controller.

