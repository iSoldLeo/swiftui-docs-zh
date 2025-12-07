--- 来源：https://developer.apple.com/documentation/SwiftUI/WKHostingController/updateBodyIfNeeded()

抓取时间：2025-12-03T07:01:20Z

---

# updateBodyIfNeeded()

**实例方法**

如果存在待处理的更新，则立即更新界面控制器的视图集。

## 声明

```swift
@MainActor @preconcurrency func updateBodyIfNeeded()
```

## 说明

调用此方法会强制宿主控制器更新其当前视图集，但仅当存在待处理的更改时才会执行。如果没有待处理的更改，则此方法不执行任何操作。

要将界面控制器标记为需要更新，请调用 [setNeedsBodyUpdate()](setNeedsBodyUpdate.zh-Hans.md)。

## 更新根视图

- **setNeedsBodyUpdate()**：使当前 SwiftUI 视图失效，并在下一个周期触发更新。


---
source: https://developer.apple.com/documentation/SwiftUI/WKHostingController/updateBodyIfNeeded()
crawled: 2025-12-03T07:01:20Z
---

# updateBodyIfNeeded()

**Instance Method**

Updates the interface controller’s set of views immediately, if updates are pending.

## Declaration

```swift
@MainActor @preconcurrency func updateBodyIfNeeded()
```

## Discussion

Calling this method forces the hosting controller to update its current set of views, but only if there are pending changes. If there are no pending changes, this method does nothing.

To mark the interface controller as needing an update, call [setNeedsBodyUpdate()](setNeedsBodyUpdate.zh-Hans.md).

## Updating the root view

- **setNeedsBodyUpdate()**: Invalidates the current SwiftUI views and triggers an update during the next cycle.

