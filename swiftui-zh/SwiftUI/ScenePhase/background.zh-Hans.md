--- 来源：https://developer.apple.com/documentation/SwiftUI/ScenePhase/background

抓取时间：2025-12-03T05:31:15Z

---

# ScenePhase.background

**Case**

场景当前在用户界面中不可见。

## 声明

```swift
case background
```

## 讨论

在 `background` 阶段，应尽可能减少场景的操作。`background` 阶段可能在终止之前，因此进入此状态后应立即执行任何清理工作。例如，关闭所有打开的文件和网络连接。但是，场景也可能从后台返回到 [active](active.zh-Hans.md) 阶段。

预期进入 `background` 阶段的应用会终止。

## 获取场景阶段

- **ScenePhase.active**：场景位于前景且可交互。

- **ScenePhase.inactive**：场景位于前景，但应暂停运行。


---
source: https://developer.apple.com/documentation/SwiftUI/ScenePhase/background
crawled: 2025-12-03T05:31:15Z
---

# ScenePhase.background

**Case**

The scene isn’t currently visible in the UI.

## Declaration

```swift
case background
```

## Discussion

Do as little as possible in a scene that’s in the `background` phase. The `background` phase can precede termination, so do any cleanup work immediately upon entering this state. For example, close any open files and network connections. However, a scene can also return to the [active](active.zh-Hans.md) phase from the background.

Expect an app that enters the `background` phase to terminate.

## Getting scene phases

- **ScenePhase.active**: The scene is in the foreground and interactive.
- **ScenePhase.inactive**: The scene is in the foreground but should pause its work.

