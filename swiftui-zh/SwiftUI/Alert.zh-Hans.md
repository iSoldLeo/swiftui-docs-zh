---
来源： https://developer.apple.com/documentation/SwiftUI/Alert
抓取时间： 2025-12-02T17:31:02Z
---

# 警报

**Structure**

警报演示的表示。

## 声明

```swift
struct Alert
```

## 概览

当您希望用户根据应用程序或系统的状态采取行动时，请使用警报。如果希望用户根据自己的操作做出选择，请使用[ActionSheet](ActionSheet.zh-Hans.md)代替。

您可以使用[alert(isPresented:content:)](View/alert_isPresented_content.zh-Hans.md) 视图修饰符来创建警报，只要绑定的`isPresented` 值为`true`，警报就会出现。您向该修改器提供的`content` 闭包将生成`Alert` 类型的自定义实例。

在下面的示例中，一个按钮通过更新与警报绑定的本地`showAlert` 属性，在被点击时显示一个简单的警报。

```swift
@State private var showAlert = false
var body: some View {
    Button("Tap to show alert") {
        showAlert = true
    }
    .alert(isPresented: $showAlert) {
        Alert(
            title: Text("Current Location Not Available"),
            message: Text("Your current location can’t be " +
                            "determined at this time.")
        )
    }
}
```



要自定义警报，可添加[Button](Alert/Button.zh-Hans.md) 类型的实例，该类型为取消和执行破坏性操作等常见任务提供标准化按钮。下面的示例使用了两个按钮：一个是标有 "再试一次 "的默认按钮，用于调用`saveWorkoutData` 方法；另一个是 "删除 "按钮，用于调用破坏性的`deleteWorkoutData` 方法。

```swift
@State private var showAlert = false
var body: some View {
    Button("Tap to show alert") {
        showAlert = true
    }
    .alert(isPresented: $showAlert) {
        Alert(
            title: Text("Unable to Save Workout Data"),
            message: Text("The connection to the server was lost."),
            primaryButton: .default(
                Text("Try Again"),
                action: saveWorkoutData
            ),
            secondaryButton: .destructive(
                Text("Delete"),
                action: deleteWorkoutData
            )
        )
    }
}
```



当用户点击警报中的某个按钮时，警报通过将绑定的 `isPresented` 值设回 `false` 来处理自己的解除。

## 创建警报

- **init(title:message:dismissButton:)**：用一个按钮创建警报。
- **init(title:message:primaryButton:secondaryButton:)**：用两个按钮创建警报。
- **sideBySideButtons(title:message:primaryButton:secondaryButton:)**：创建并排按钮提示。

## 指定按钮类型

- **Alert.Button**：表示警报演示操作的按钮。

## 过时的模式演示

- **ActionSheet**：表示动作表单演示的按钮。


---
source: https://developer.apple.com/documentation/SwiftUI/Alert
crawled: 2025-12-02T17:31:02Z
---

# Alert

**Structure**

A representation of an alert presentation.

## Declaration

```swift
struct Alert
```

## Overview

Use an alert when you want the user to act in response to the state of the app or system. If you want the user to make a choice in response to their action, use an [ActionSheet](ActionSheet.zh-Hans.md) instead.

You show an alert by using the [alert(isPresented:content:)](View/alert_isPresented_content.zh-Hans.md) view modifier to create an alert, which then appears whenever the bound `isPresented` value is `true`. The `content` closure you provide to this modifer produces a customized instance of the `Alert` type.

In the following example, a button presents a simple alert when tapped, by updating a local `showAlert` property that binds to the alert.

```swift
@State private var showAlert = false
var body: some View {
    Button("Tap to show alert") {
        showAlert = true
    }
    .alert(isPresented: $showAlert) {
        Alert(
            title: Text("Current Location Not Available"),
            message: Text("Your current location can’t be " +
                            "determined at this time.")
        )
    }
}
```



To customize the alert, add instances of the [Button](Alert/Button.zh-Hans.md) type, which provides standardized buttons for common tasks like canceling and performing destructive actions. The following example uses two buttons: a default button labeled “Try Again” that calls a `saveWorkoutData` method, and a “Delete” button that calls a destructive `deleteWorkoutData` method.

```swift
@State private var showAlert = false
var body: some View {
    Button("Tap to show alert") {
        showAlert = true
    }
    .alert(isPresented: $showAlert) {
        Alert(
            title: Text("Unable to Save Workout Data"),
            message: Text("The connection to the server was lost."),
            primaryButton: .default(
                Text("Try Again"),
                action: saveWorkoutData
            ),
            secondaryButton: .destructive(
                Text("Delete"),
                action: deleteWorkoutData
            )
        )
    }
}
```



The alert handles its own dismissal when the user taps one of the buttons in the alert, by setting the bound `isPresented` value back to `false`.

## Creating an alert

- **init(title:message:dismissButton:)**: Creates an alert with one button.
- **init(title:message:primaryButton:secondaryButton:)**: Creates an alert with two buttons.
- **sideBySideButtons(title:message:primaryButton:secondaryButton:)**: Creates a side by side button alert.

## Specifying the button type

- **Alert.Button**: A button that represents an operation of an alert presentation.

## Deprecated modal presentations

- **ActionSheet**: A representation of an action sheet presentation.

