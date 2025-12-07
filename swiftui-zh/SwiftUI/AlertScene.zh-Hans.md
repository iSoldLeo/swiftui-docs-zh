---
来源： https://developer.apple.com/documentation/SwiftUI/AlertScene
抓取时间： 2025-12-02T17:30:23Z
---

# AlertScene

**Structure**

将自己渲染为独立警报对话框的场景。

## 声明

```swift
struct AlertScene<Actions, Message> where Actions : View, Message : View
```

## 概览

警报场景不依附于任何特定窗口，而是显示在当前显示屏的中央。在与应用程序进行任何进一步交互之前，必须先退出对话框。

```swift
@main
struct MyApp: App {
    @State var showLoginAlert = true
    @State var loggedIn = false

    var body: some Scene {
        Window("Welcome User Window", id:"WelcomeWindow") {
            ...
        }
        .defaultLaunchBehavior(loggedIn ? .presented : .suppressed)

        AlertScene("Login Required", isPresented: $showLoginAlert) {
            Button("OK") {
                ...
            }
        }
    }
}
```

ViewBuilder 中的所有操作都将解除警报。与警报修改器一样，您可以使用 `.cancel` 或 `.destructive` 来确定按钮的作用。如果没有任何操作，我们将自动包含一个确定按钮，用于解散。

## 初始化程序

- **init(_:isPresented:actions:)**：创建一个带有标题和一组操作的警报场景。
- **init(_:isPresented:actions:message:)**：创建带有标题、一组操作和一条信息的警报场景。
- **init(_:isPresented:presenting:actions:)**：创建警报场景，使用给定的数据生成带有标题和一组操作的警报内容。请注意，这将代表您创建一个文本视图。
- **init(_:isPresented:presenting:actions:message:)**：创建警报场景，使用给定的数据生成带有标题、操作集和消息的警报内容。请注意，这将代表您创建一个文本视图。

## 呈现警报

- **alert(_:isPresented:actions:)**：当给定条件为真时显示警报，标题使用文本视图。
- **alert(_:isPresented:presenting:actions:)**：使用给定数据生成警报内容，并使用文本视图作为标题显示警报。
- **alert(isPresented:error:actions:)**：出现错误时发出警报。
- **alert(_:isPresented:actions:message:)**：使用文本视图作为标题，在给定条件为真时显示带有信息的警报。
- **alert(_:isPresented:presenting:actions:message:)**：使用给定数据生成警报内容，并使用文本视图作为标题，显示带信息的警报。
- **alert(isPresented:error:actions:message:)**：当出现错误时，显示带信息的警报。

## 符合

- 场景


---
source: https://developer.apple.com/documentation/SwiftUI/AlertScene
crawled: 2025-12-02T17:30:23Z
---

# AlertScene

**Structure**

A scene that renders itself as a standalone alert dialog.

## Declaration

```swift
struct AlertScene<Actions, Message> where Actions : View, Message : View
```

## Overview

Alert scenes are not attached to any particular window, and present themselves in the center of the current display. The dialog must be dismissed before any further interaction with the app is permitted.

```swift
@main
struct MyApp: App {
    @State var showLoginAlert = true
    @State var loggedIn = false

    var body: some Scene {
        Window("Welcome User Window", id:"WelcomeWindow") {
            ...
        }
        .defaultLaunchBehavior(loggedIn ? .presented : .suppressed)

        AlertScene("Login Required", isPresented: $showLoginAlert) {
            Button("OK") {
                ...
            }
        }
    }
}
```

All actions present in the ViewBuilder will dismiss the alert. Like the alert modifier, you can determine the role of the buttons with `.cancel` or `.destructive`. If no actions are present, we will automatically include an OK button for dismissal.

## Initializers

- **init(_:isPresented:actions:)**: Creates an alert scene with a title and a set of actions.
- **init(_:isPresented:actions:message:)**: Creates an alert scene with a title, a set of actions, and a message.
- **init(_:isPresented:presenting:actions:)**: Creates an alert scene, using the given data to produce the alert’s content with a title, and a set of actions. Note that this creates a text view on your behalf.
- **init(_:isPresented:presenting:actions:message:)**: Creates an alert scene, using the given data to produce the alert’s content with a title, a set of actions, and a message. Note that this creates a text view on your behalf.

## Presenting an alert

- **alert(_:isPresented:actions:)**: Presents an alert when a given condition is true, using a text view for the title.
- **alert(_:isPresented:presenting:actions:)**: Presents an alert using the given data to produce the alert’s content and a text view as a title.
- **alert(isPresented:error:actions:)**: Presents an alert when an error is present.
- **alert(_:isPresented:actions:message:)**: Presents an alert with a message when a given condition is true using a text view as a title.
- **alert(_:isPresented:presenting:actions:message:)**: Presents an alert with a message using the given data to produce the alert’s content and a text view for a title.
- **alert(isPresented:error:actions:message:)**: Presents an alert with a message when an error is present.

## Conforms To

- Scene

