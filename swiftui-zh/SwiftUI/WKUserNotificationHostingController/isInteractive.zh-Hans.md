---
来源： https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController/isInteractive
抓取时间： 2025-12-03T07:01:24Z
---

# isInteractive

**类型属性**

通知是否应接受用户输入。

## 声明

```swift
@MainActor @preconcurrency class var isInteractive: Bool { get }
```

## 讨论

默认值为 `false`

## 配置通知

- **coalescedDescriptionFormat**：同一类型的多个通知同时到达时要显示的格式字符串。如果指定自定义字符串，则可以使用 %d 变量来反映通知的数量。`nil`格式将作为系统默认格式。
- **sashColor**：在长外观界面的窗格内使用的颜色。如果`nil`，斜线将使用系统默认颜色。
- **subtitleColor**：应用于简短外观界面中显示的字幕文本的颜色。如果`nil`，文本将使用默认系统颜色。
- **titleColor**：应用于窗格中显示的文本的颜色。如果 `nil`，文本将使用系统默认颜色。
- **wantsSashBlur**：如果纱带应包括背景模糊效果。


---
source: https://developer.apple.com/documentation/SwiftUI/WKUserNotificationHostingController/isInteractive
crawled: 2025-12-03T07:01:24Z
---

# isInteractive

**Type Property**

If the notification should accept user input.

## Declaration

```swift
@MainActor @preconcurrency class var isInteractive: Bool { get }
```

## Discussion

Default value is `false`

## Configuring the notification

- **coalescedDescriptionFormat**: The format string to display when multiple notifications of the same type arrive simultaneously. If you specify a custom string, you can use the %d variable to reflect the number of notifications. If `nil` format will be the system default.
- **sashColor**: Color to use within the sash of the long look interface. If `nil` the sash will be the default system color.
- **subtitleColor**: The color to apply to the subtitle text displayed in the short look interface. If `nil` the text will be the default system color.
- **titleColor**: The color to apply to the text displayed in the sash. If `nil` the text will be the default system color.
- **wantsSashBlur**: If the sash should include a blur over the background.

