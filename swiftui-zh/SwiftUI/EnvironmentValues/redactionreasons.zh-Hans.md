---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/redactionreasons
抓取时间： 2025-12-04T13:10:40Z
---

# redactionReasons

**实例属性**

应用于视图层次结构的当前编辑原因。

## 声明

```swift
var redactionReasons: RedactionReasons { get set }
```

## Redacting private content

- 为 "始终保持开启 "状态设计应用程序**：自定义 watchOS 应用程序的用户界面，以便连续显示。
- **privacySensitive(_:)**：将视图标记为包含敏感的私人用户数据。
- **redacted(reason:)**：添加对该视图层次结构应用编辑的理由。
- **unredacted()**：删除对该视图层次结构应用节录的任何理由。
- **isSceneCaptured**：当前捕获状态。
- **RedactionReasons**：当前捕获状态：对屏幕上显示的数据进行编辑的原因。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/redactionreasons
crawled: 2025-12-04T13:10:40Z
---

# redactionReasons

**Instance Property**

The current redaction reasons applied to the view hierarchy.

## Declaration

```swift
var redactionReasons: RedactionReasons { get set }
```

## Redacting private content

- **Designing your app for the Always On state**: Customize your watchOS app’s user interface for continuous display.
- **privacySensitive(_:)**: Marks the view as containing sensitive, private user data.
- **redacted(reason:)**: Adds a reason to apply a redaction to this view hierarchy.
- **unredacted()**: Removes any reason to apply a redaction to this view hierarchy.
- **isSceneCaptured**: The current capture state.
- **RedactionReasons**: The reasons to apply a redaction to data displayed on screen.

