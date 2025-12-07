---
source: https://developer.apple.com/documentation/SwiftUI/Alert/init(title:message:primaryButton:secondaryButton:)
抓取时间：2025-12-01T10:51:51Z


# init(title:message:primaryButton:secondaryButton:)

**Initializer**

创建带有两个按钮的警报。

## 声明

```swift
init(title: Text, message: Text? = nil, primaryButton: Alert.Button, secondaryButton: Alert.Button)
```

## 参数

- **title**：警报标题。
- **message**：要在警报正文中显示的信息。
- **primaryButton**：警报中要显示的第一个按钮。
- **secondaryButton**： 在警报中显示的第一个按钮：警报中要显示的第二个按钮。

## 讨论

系统决定按钮的视觉顺序。

## 创建警报

- **init(title:message:dismissButton:)**：用一个按钮创建警报。
- **sideBySideButtons(title:message:primaryButton:secondaryButton:)**：创建并排按钮警报。


---
source: https://developer.apple.com/documentation/SwiftUI/Alert/init(title:message:primaryButton:secondaryButton:)
crawled: 2025-12-01T10:51:51Z
---

# init(title:message:primaryButton:secondaryButton:)

**Initializer**

Creates an alert with two buttons.

## Declaration

```swift
init(title: Text, message: Text? = nil, primaryButton: Alert.Button, secondaryButton: Alert.Button)
```

## Parameters

- **title**: The title of the alert.
- **message**: The message to display in the body of the alert.
- **primaryButton**: The first button to show in the alert.
- **secondaryButton**: The second button to show in the alert.

## Discussion

The system determines the visual ordering of the buttons.

## Creating an alert

- **init(title:message:dismissButton:)**: Creates an alert with one button.
- **sideBySideButtons(title:message:primaryButton:secondaryButton:)**: Creates a side by side button alert.

