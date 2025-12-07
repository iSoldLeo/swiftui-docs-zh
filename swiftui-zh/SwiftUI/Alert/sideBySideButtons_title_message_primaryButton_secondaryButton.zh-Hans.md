---
来源：https://developer.apple.com/documentation/SwiftUI/Alert/sideBySideButtons(title:message:primaryButton:secondaryButton:)
抓取时间：2025-12-03T06:02:54Z


# sideBySideButtons(title:message:primaryButton:secondaryButton:)

**类型方法***

创建并排按钮提示。

## 声明

```swift
static func sideBySideButtons(title: Text, message: Text? = nil, primaryButton: Alert.Button, secondaryButton: Alert.Button) -> Alert
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
- **init(title:message:primaryButton:secondaryButton:)**：创建带有两个按钮的警报。


---
source: https://developer.apple.com/documentation/SwiftUI/Alert/sideBySideButtons(title:message:primaryButton:secondaryButton:)
crawled: 2025-12-03T06:02:54Z
---

# sideBySideButtons(title:message:primaryButton:secondaryButton:)

**Type Method**

Creates a side by side button alert.

## Declaration

```swift
static func sideBySideButtons(title: Text, message: Text? = nil, primaryButton: Alert.Button, secondaryButton: Alert.Button) -> Alert
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
- **init(title:message:primaryButton:secondaryButton:)**: Creates an alert with two buttons.

