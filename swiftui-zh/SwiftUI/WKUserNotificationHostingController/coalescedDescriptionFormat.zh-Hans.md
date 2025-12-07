---
来源： https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController/coalescedDescriptionFormat
抓取时间： 2025-12-03T07:01:23Z
---

# coalescedDescriptionFormat

**类型属性**

同一类型的多个通知同时到达时显示的格式字符串。如果指定自定义字符串，可以使用 %d 变量来反映通知的数量。如果 `nil` 格式将是系统默认格式。

## 声明

```swift
@MainActor @preconcurrency class var coalescedDescriptionFormat: String? { get }
```

## 讨论

默认值为 `nil`

## 配置通知

- **isInteractive**：如果通知应接受用户输入。
- **sashColor**：在长条形界面的斜线内使用的颜色。如果 `nil`，边框将使用系统默认颜色。
- **subtitleColor**：应用于简短外观界面中显示的字幕文本的颜色。如果`nil`，文本将使用默认系统颜色。
- **titleColor**：应用于窗格中显示的文本的颜色。如果 `nil`，文本将使用系统默认颜色。
- **wantsSashBlur**：如果纱带应包括背景模糊效果。


---
source: https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController/coalescedDescriptionFormat
crawled: 2025-12-03T07:01:23Z
---

# coalescedDescriptionFormat

**Type Property**

The format string to display when multiple notifications of the same type arrive simultaneously. If you specify a custom string, you can use the %d variable to reflect the number of notifications. If `nil` format will be the system default.

## Declaration

```swift
@MainActor @preconcurrency class var coalescedDescriptionFormat: String? { get }
```

## Discussion

Default value is `nil`

## Configuring the notification

- **isInteractive**: If the notification should accept user input.
- **sashColor**: Color to use within the sash of the long look interface. If `nil` the sash will be the default system color.
- **subtitleColor**: The color to apply to the subtitle text displayed in the short look interface. If `nil` the text will be the default system color.
- **titleColor**: The color to apply to the text displayed in the sash. If `nil` the text will be the default system color.
- **wantsSashBlur**: If the sash should include a blur over the background.

