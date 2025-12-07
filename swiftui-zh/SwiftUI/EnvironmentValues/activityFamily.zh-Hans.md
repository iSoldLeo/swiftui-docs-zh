---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/activityFamily
抓取时间： 2025-12-02T17:45:38Z
---

# 活动家族

**实例属性**

当前实时活动的尺寸系列。

## 声明

```swift
var activityFamily: ActivityFamily { get set }
```

## 讨论

您在一台设备上启动的实时活动也可能出现在一台远程设备上，该设备会以不同的族大小呈现实时活动。因此，它会根据设备和出现的位置为特定族渲染。例如，在 iOS 或 iPadOS 锁屏上呈现时，当前的族是 doc://com.apple.comdumentation/documentation/WidgetKit/ActivityFamily/medium。

使用 [doc://com.apple.documentation/documentation/SwiftUI/WidgetConfiguration/supplementalActivityFamilies(_:)] 可选择加入并允许你的实时活动使用其他族呈现。

## 配置实时活动

- **activitySystemActionForegroundColor(_:)**：系统在锁定屏幕上实时活动旁边显示的辅助操作按钮的文字颜色。
- **activityBackgroundTint(_:)**：设置锁定屏幕上显示的实时活动背景的色调。
- **isActivityFullscreen**：布尔值，表示实时活动是否以全屏显示。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/activityFamily
crawled: 2025-12-02T17:45:38Z
---

# activityFamily

**Instance Property**

The size family of the current Live Activity.

## Declaration

```swift
var activityFamily: ActivityFamily { get set }
```

## Discussion

A Live Activity you initiate on one device can also appear on a remote device that renders the Live Activity in a different family size. As a result, it renders for a specific family, depending on both the device and the location in which it appears. For example, when rendering on the iOS or iPadOS Lock Screen, the current family is doc://com.apple.comdumentation/documentation/WidgetKit/ActivityFamily/medium.

Use [doc://com.apple.documentation/documentation/SwiftUI/WidgetConfiguration/supplementalActivityFamilies(_:)] to opt in and allow your Live Activity to render with additional families.

## Configuring a Live Activity

- **activitySystemActionForegroundColor(_:)**: The text color for the auxiliary action button that the system shows next to a Live Activity on the Lock Screen.
- **activityBackgroundTint(_:)**: Sets the tint color for the background of a Live Activity that appears on the Lock Screen.
- **isActivityFullscreen**: A Boolean value that indicates whether the Live Activity appears in a full-screen presentation.

