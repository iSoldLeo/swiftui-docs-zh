---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isActivityFullscreen
抓取时间： 2025-12-02T17:45:37Z
---

# isActivityFullscreen

**实例属性**

布尔值，表示实时活动是否以全屏显示。

## 声明

```swift
@backDeployed(before: iOS 17.0)
var isActivityFullscreen: Bool { get }
```

## 讨论

当实时活动充满整个屏幕时，系统会扩展您用[doc://com.apple.documentation/documentation/SwiftUI/View/activityBackgroundTint(_:)] 修改器设置的背景色调颜色，使其充满屏幕。

请注意，在 iOS 16 中，该环境变量始终为 `false`。

## 配置实时活动

- **activitySystemActionForegroundColor(_:)**：系统在锁定屏幕上的实时活动旁显示的辅助操作按钮的文字颜色。
- **activityBackgroundTint(_:)**：设置锁定屏幕上显示的实时活动背景的色调。
- **activityFamily**：当前实时活动的尺寸系列。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isActivityFullscreen
crawled: 2025-12-02T17:45:37Z
---

# isActivityFullscreen

**Instance Property**

A Boolean value that indicates whether the Live Activity appears in a full-screen presentation.

## Declaration

```swift
@backDeployed(before: iOS 17.0)
var isActivityFullscreen: Bool { get }
```

## Discussion

When a Live Activity fills the entire screen, the system extends the background tint color you set with the [doc://com.apple.documentation/documentation/SwiftUI/View/activityBackgroundTint(_:)] modifier to fill the screen.

Note that this environment variable is always `false` in iOS 16.

## Configuring a Live Activity

- **activitySystemActionForegroundColor(_:)**: The text color for the auxiliary action button that the system shows next to a Live Activity on the Lock Screen.
- **activityBackgroundTint(_:)**: Sets the tint color for the background of a Live Activity that appears on the Lock Screen.
- **activityFamily**: The size family of the current Live Activity.

