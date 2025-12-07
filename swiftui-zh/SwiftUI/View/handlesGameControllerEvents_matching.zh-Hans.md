--- 来源：https://developer.apple.com/documentation/SwiftUI/View/handlesGameControllerEvents(matching:)

抓取时间：2025-12-02T17:23:56Z

---

# handlesGameControllerEvents(matching:)

**实例方法**

指定当视图或其子视图获得焦点时，应通过 GameController 框架传递的游戏控制器事件。

## 声明

```swift
nonisolated func handlesGameControllerEvents(matching types: GCUIEventTypes) -> some View

```

## 讨论

```swift
SpriteView(scene: MyGameScene())
.handlesGameControllerEvents(matching: .gamepad)
.focused(true)
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/handlesGameControllerEvents(matching:)
crawled: 2025-12-02T17:23:56Z
---

# handlesGameControllerEvents(matching:)

**Instance Method**

Specifies the game controllers events which should be delivered through the GameController framework when the view, or one of its descendants has focus.

## Declaration

```swift
nonisolated func handlesGameControllerEvents(matching types: GCUIEventTypes) -> some View

```

## Discussion

```swift
SpriteView(scene: MyGameScene())
.handlesGameControllerEvents(matching: .gamepad)
.focused(true)
```

