---
来源： https://developer.apple.com/documentation/SwiftUI/ActionSheet
抓取时间： 2025-12-02T17:31:03Z
---

# 行动表

**Structure**

行动表单演示的表示方法。

## 声明

```swift
struct ActionSheet
```

## 概览

当您希望用户根据自己的操作在两个或多个选项中做出选择时，请使用操作表。如果您希望用户根据应用程序或系统的状态（而不是用户的操作）进行操作，请使用 [Alert](Alert.zh-Hans.md) 代替。

您可以使用[actionSheet(isPresented:content:)](View/actionSheet_isPresented_content.zh-Hans.md) 视图修饰符创建一个操作页来显示操作页，只要绑定的`isPresented` 值为`true`，操作页就会出现。您为该修饰符提供的`content` 闭包将生成`ActionSheet` 类型的自定义实例。为了提供选项，请创建[Button](ActionSheet/Button.zh-Hans.md) 的实例，以区分普通选项、破坏性选项和取消用户的原始操作。

当用户点击操作页中的按钮时，操作页会通过将绑定的`isPresented` 值设置回`false` 来处理其取消操作。

下面的示例创建了一个带有三个选项的操作表：取消按钮、破坏按钮和默认按钮。其中第二个和第三个调用方法分别命名为 `overwriteWorkout` 和 `appendWorkout`。

```swift
@State private var showActionSheet = false
var body: some View {
    Button("Tap to show action sheet") {
        showActionSheet = true
    }
    .actionSheet(isPresented: $showActionSheet) {
        ActionSheet(title: Text("Resume Workout Recording"),
                    message: Text("Choose a destination for workout data"),
                    buttons: [
                        .cancel(),
                        .destructive(
                            Text("Overwrite Current Workout"),
                            action: overwriteWorkout
                        ),
                        .default(
                            Text("Append to Current Workout"),
                            action: appendWorkout
                        )
                    ]
        )
    }
}
```

系统可能会按照`buttons` 数组中出现的项目顺序进行解释，以适应平台惯例。在本例中，"取消 "按钮是数组中的第一个成员，但操作页将其置于操作页底部的标准位置。



## 创建操作页

- **init(title:message:buttons:)**：用提供的按钮创建一个操作页。

## 指定按钮类型

- **ActionSheet.Button**：表示操作表演示操作的按钮。

## 过时的模式演示

- **Alert**：表示警报的演示文稿。


---
source: https://developer.apple.com/documentation/SwiftUI/ActionSheet
crawled: 2025-12-02T17:31:03Z
---

# ActionSheet

**Structure**

A representation of an action sheet presentation.

## Declaration

```swift
struct ActionSheet
```

## Overview

Use an action sheet when you want the user to make a choice between two or more options, in response to their own action. If you want the user to act in response to the state of the app or the system, rather than a user action, use an [Alert](Alert.zh-Hans.md) instead.

You show an action sheet by using the [actionSheet(isPresented:content:)](View/actionSheet_isPresented_content.zh-Hans.md) view modifier to create an action sheet, which then appears whenever the bound `isPresented` value is `true`. The `content` closure you provide to this modifier produces a customized instance of the `ActionSheet` type. To supply the options, create instances of [Button](ActionSheet/Button.zh-Hans.md) to distinguish between ordinary options, destructive options, and cancellation of the user’s original action.

The action sheet handles its dismissal by setting the bound `isPresented` value back to `false` when the user taps a button in the action sheet.

The following example creates an action sheet with three options: a Cancel button, a destructive button, and a default button. The second and third of these call methods are named `overwriteWorkout` and `appendWorkout`, respectively.

```swift
@State private var showActionSheet = false
var body: some View {
    Button("Tap to show action sheet") {
        showActionSheet = true
    }
    .actionSheet(isPresented: $showActionSheet) {
        ActionSheet(title: Text("Resume Workout Recording"),
                    message: Text("Choose a destination for workout data"),
                    buttons: [
                        .cancel(),
                        .destructive(
                            Text("Overwrite Current Workout"),
                            action: overwriteWorkout
                        ),
                        .default(
                            Text("Append to Current Workout"),
                            action: appendWorkout
                        )
                    ]
        )
    }
}
```

The system may interpret the order of items as they appear in the `buttons` array to accommodate platform conventions. In this example, the Cancel button is the first member of the array, but the action sheet puts it in its standard position at the bottom of the sheet.



## Creating an action sheet

- **init(title:message:buttons:)**: Creates an action sheet with the provided buttons.

## Specifying the button type

- **ActionSheet.Button**: A button representing an operation of an action sheet presentation.

## Deprecated modal presentations

- **Alert**: A representation of an alert presentation.

