--- 来源：https://developer.apple.com/documentation/SwiftUI/ScenePhase/active
抓取时间：2025-12-03T05:31:14Z

---

# ScenePhase.active

**Case**

场景处于前台且可交互。

## 声明

```swift
case active
```

## 讨论

活动场景不一定位于最前面。例如，即使 macOS 窗口当前没有焦点，它也可能处于活动状态。尽管如此，所有场景在此阶段都应正常运行。

处于此阶段的应用或自定义场景至少包含一个活动场景实例。

## 获取场景阶段

- **ScenePhase.inactive**：场景处于前台，但应暂停其工作。

- **ScenePhase.background**：当前场景在用户界面中不可见。


---
source: https://developer.apple.com/documentation/SwiftUI/ScenePhase/active
crawled: 2025-12-03T05:31:14Z
---

# ScenePhase.active

**Case**

The scene is in the foreground and interactive.

## Declaration

```swift
case active
```

## Discussion

An active scene isn’t necessarily front-most. For example, a macOS window might be active even if it doesn’t currently have focus. Nevertheless, all scenes should operate normally in this phase.

An app or custom scene in this phase contains at least one active scene instance.

## Getting scene phases

- **ScenePhase.inactive**: The scene is in the foreground but should pause its work.
- **ScenePhase.background**: The scene isn’t currently visible in the UI.

