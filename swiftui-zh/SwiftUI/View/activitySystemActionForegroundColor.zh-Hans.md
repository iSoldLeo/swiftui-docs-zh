--- 来源：https://developer.apple.com/documentation/SwiftUI/View/activitySystemActionForegroundColor(_:)

抓取时间：2025-11-30T21:30:34Z

---

# activitySystemActionForegroundColor(_:)

**实例方法**

用于设置系统在锁屏界面上显示的 Live Activity 旁边辅助操作按钮的文本颜色。

## 声明

```swift
@MainActor @preconcurrency func activitySystemActionForegroundColor(_ color: Color?) -> some View

```

## 参数

- **color**：要使用的文本颜色。传递 `nil` 以使用系统默认颜色。

## 配置 Live Activity

- **activityBackgroundTint(_:)**：设置显示在锁屏界面上的 Live Activity 的背景色调。

- **isActivityFullscreen**：一个布尔值，指示实时活动是否以全屏模式显示。

- **activityFamily**：当前实时活动的尺寸范围。


---
source: https://developer.apple.com/documentation/SwiftUI/View/activitySystemActionForegroundColor(_:)
crawled: 2025-11-30T21:30:34Z
---

# activitySystemActionForegroundColor(_:)

**Instance Method**

The text color for the auxiliary action button that the system shows next to a Live Activity on the Lock Screen.

## Declaration

```swift
@MainActor @preconcurrency func activitySystemActionForegroundColor(_ color: Color?) -> some View

```

## Parameters

- **color**: The text color to use. Pass `nil` to use the system’s default color.

## Configuring a Live Activity

- **activityBackgroundTint(_:)**: Sets the tint color for the background of a Live Activity that appears on the Lock Screen.
- **isActivityFullscreen**: A Boolean value that indicates whether the Live Activity appears in a full-screen presentation.
- **activityFamily**: The size family of the current Live Activity.

