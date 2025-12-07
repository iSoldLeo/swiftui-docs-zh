--- 来源：https://developer.apple.com/documentation/SwiftUI/WKHostingController/setNeedsBodyUpdate()

抓取时间：2025-12-03T07:01:21Z

---

# setNeedsBodyUpdate()

**实例方法**

使当前 SwiftUI 视图失效，并在下一个更新周期触发更新。

## 声明

```swift
@MainActor @preconcurrency func setNeedsBodyUpdate()
```

## 说明

调用此方法可将宿主控制器的视图标记为需要更新。在下一个更新周期，宿主控制器将从其 [body](body.zh-Hans.md) 属性中获取更新后的视图集。

## 更新根视图

- **updateBodyIfNeeded()**：如果存在待处理的更新，则立即更新界面控制器的视图集。


---
source: https://developer.apple.com/documentation/SwiftUI/WKHostingController/setNeedsBodyUpdate()
crawled: 2025-12-03T07:01:21Z
---

# setNeedsBodyUpdate()

**Instance Method**

Invalidates the current SwiftUI views and triggers an update during the next cycle.

## Declaration

```swift
@MainActor @preconcurrency func setNeedsBodyUpdate()
```

## Discussion

Call this method to mark the views of the hosting controller as needing an update. During the next update cycle, the hosting controller fetches an updated set of views from its [body](body.zh-Hans.md) property.

## Updating the root view

- **updateBodyIfNeeded()**: Updates the interface controller’s set of views immediately, if updates are pending.

