--- 来源：https://developer.apple.com/documentation/SwiftUI/ScenePhase/inactive
抓取时间：2025-12-03T05:31:14Z

---

# ScenePhase.inactive

**Case**

场景位于前台，但应暂停运行。

## 声明

```swift
case inactive
```

## 讨论

处于此阶段的场景不接收事件，应暂停计时器并释放所有不必要的资源。该场景可能完全隐藏在用户界面中，或用户无法访问。在 macOS 中，场景只是暂时经过此阶段，然后进入 [background](background.zh-Hans.md) 阶段。

处于此阶段的应用或自定义场景不包含任何 [active](active.zh-Hans.md) 阶段的场景实例。

## 获取场景状态

- **ScenePhase.active**：场景位于前景且可交互。

- **ScenePhase.background**：场景当前在用户界面中不可见。


---
source: https://developer.apple.com/documentation/SwiftUI/ScenePhase/inactive
crawled: 2025-12-03T05:31:14Z
---

# ScenePhase.inactive

**Case**

The scene is in the foreground but should pause its work.

## Declaration

```swift
case inactive
```

## Discussion

A scene in this phase doesn’t receive events and should pause timers and free any unnecessary resources. The scene might be completely hidden in the user interface or otherwise unavailable to the user. In macOS, scenes only pass through this phase temporarily on their way to the [background](background.zh-Hans.md) phase.

An app or custom scene in this phase contains no scene instances in the [active](active.zh-Hans.md) phase.

## Getting scene phases

- **ScenePhase.active**: The scene is in the foreground and interactive.
- **ScenePhase.background**: The scene isn’t currently visible in the UI.

