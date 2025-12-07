--- 来源：https://developer.apple.com/documentation/SwiftUI/View/activityBackgroundTint(_:)

抓取时间：2025-11-30T21:30:35Z

---

# activityBackgroundTint(_:)

**实例方法**

设置锁定屏幕上显示的 Live Activity 的背景色调。

## 声明

```swift
@MainActor @preconcurrency func activityBackgroundTint(_ color: Color?) -> some View

```

## 参数

- **color**：要应用的背景色调。要使用系统默认的背景材质，请传递 `nil`。

## 讨论

设置自定义背景色调时，请考虑为用户在锁定屏幕上用于结束 Live Activity 的辅助按钮设置自定义文本颜色。要设置自定义文本颜色，请使用 [doc://com.apple.documentation/documentation/SwiftUI/View/activitySystemActionForegroundColor(_:)] 视图修饰符。

## 配置动态活动

- **activitySystemActionForegroundColor(_:)**：系统在锁屏界面动态活动旁边显示的辅助操作按钮的文本颜色。

- **isActivityFullscreen**：一个布尔值，指示动态活动是否以全屏模式显示。

- **activityFamily**：当前动态活动的尺寸范围。


---
source: https://developer.apple.com/documentation/SwiftUI/View/activityBackgroundTint(_:)
crawled: 2025-11-30T21:30:35Z
---

# activityBackgroundTint(_:)

**Instance Method**

Sets the tint color for the background of a Live Activity that appears on the Lock Screen.

## Declaration

```swift
@MainActor @preconcurrency func activityBackgroundTint(_ color: Color?) -> some View

```

## Parameters

- **color**: The background tint color to apply. To use the system’s default background material, pass `nil`.

## Discussion

When you set a custom background tint color, consider setting a custom text color for the auxiliary button people use to end a Live Activity on the Lock Screen. To set a custom text color, use the [doc://com.apple.documentation/documentation/SwiftUI/View/activitySystemActionForegroundColor(_:)] view modifier.

## Configuring a Live Activity

- **activitySystemActionForegroundColor(_:)**: The text color for the auxiliary action button that the system shows next to a Live Activity on the Lock Screen.
- **isActivityFullscreen**: A Boolean value that indicates whether the Live Activity appears in a full-screen presentation.
- **activityFamily**: The size family of the current Live Activity.

