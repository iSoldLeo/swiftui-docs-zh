---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isSceneCaptured
抓取时间： 2025-12-02T17:32:57Z
---

# isSceneCaptured

**实例属性**

当前捕获状态。

## 声明

```swift
var isSceneCaptured: Bool { get set }
```

## 讨论

使用此值可确定场景是否正在被克隆到另一个目标（如在 AirPlay 期间）或正在被镜像或录制。

您的应用程序可以根据此值的变化采取适当的措施，如遮挡内容。

## 隐藏私人内容

- 为始终保持开启状态设计应用程序**：自定义 watchOS 应用程序的用户界面，以实现连续显示。
- **privacySensitive(_:)**：将视图标记为包含敏感的私人用户数据。
- **redacted(reason:)**：添加对该视图层次结构应用编辑的理由。
- **unredacted()**：删除对该视图层次结构应用节录的任何理由。
- **redactionReasons**：当前应用于视图层次结构的编辑理由。
- **RedactionReasons**：对屏幕上显示的数据应用编辑的原因。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isSceneCaptured
crawled: 2025-12-02T17:32:57Z
---

# isSceneCaptured

**Instance Property**

The current capture state.

## Declaration

```swift
var isSceneCaptured: Bool { get set }
```

## Discussion

Use this value to determine whether the scene is actively being cloned to another destination (like during AirPlay) or is being mirrored or recorded.

Your app can respond to changes in this value to take appropriate action, like obscuring content.

## Redacting private content

- **Designing your app for the Always On state**: Customize your watchOS app’s user interface for continuous display.
- **privacySensitive(_:)**: Marks the view as containing sensitive, private user data.
- **redacted(reason:)**: Adds a reason to apply a redaction to this view hierarchy.
- **unredacted()**: Removes any reason to apply a redaction to this view hierarchy.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **RedactionReasons**: The reasons to apply a redaction to data displayed on screen.

