--- 来源：https://developer.apple.com/documentation/SwiftUI/View/handlesGameControllerEvents(matching:withOptions:)

抓取时间：2025-12-02T17:23:57Z

---

# handlesGameControllerEvents(matching:withOptions:)

**实例方法**

指定当视图或其子视图获得焦点时，应通过 GameController 框架传递的游戏控制器事件。

## 声明

```swift
nonisolated func handlesGameControllerEvents(matching types: GCUIEventTypes, withOptions options: GameControllerEventHandlingOptions?) -> some View

```

## 讨论

```swift
SpriteView(scene: MyGameScene())
.handlesGameControllerEvents(matching: .gamepad, withOptions: .defaultOptions)
.focused(true)
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/handlesGameControllerEvents(matching:withOptions:)
crawled: 2025-12-02T17:23:57Z
---

# handlesGameControllerEvents(matching:withOptions:)

**Instance Method**

Specifies the game controllers events which should be delivered through the GameController framework when the view or one of its descendants has focus.

## Declaration

```swift
nonisolated func handlesGameControllerEvents(matching types: GCUIEventTypes, withOptions options: GameControllerEventHandlingOptions?) -> some View

```

## Discussion

```swift
SpriteView(scene: MyGameScene())
.handlesGameControllerEvents(matching: .gamepad, withOptions: .defaultOptions)
.focused(true)
```

