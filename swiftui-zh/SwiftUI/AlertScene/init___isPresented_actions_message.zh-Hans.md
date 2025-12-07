---
来源：https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:actions:message:)
抓取时间：2025-12-03T06:02:40Z


# init(_:isPresented:actions:message:)

**Initializer**

创建一个带有标题、一组操作和一条信息的警报场景。

## 声明

```swift
init(_ title: Text, isPresented: Binding<Bool>, @ViewBuilder actions: () -> Actions, @ViewBuilder message: () -> Message)
```

## 参数

- **title**：警报标题。
- **isPresented**：与布尔值的绑定，决定是否显示警报。当用户按下或点击警报的某个操作时，系统会将此值设为 `false` 并解除。
- **actions**：返回对话框操作的视图创建器。
- **message**：返回对话框操作的视图创建器：返回对话框信息的视图创建器。


---
source: https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:actions:message:)
crawled: 2025-12-03T06:02:40Z
---

# init(_:isPresented:actions:message:)

**Initializer**

Creates an alert scene with a title, a set of actions, and a message.

## Declaration

```swift
init(_ title: Text, isPresented: Binding<Bool>, @ViewBuilder actions: () -> Actions, @ViewBuilder message: () -> Message)
```

## Parameters

- **title**: The title of the alert.
- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **actions**: A view builder returning the actions for the dialog.
- **message**: A view builder returning the message for the dialog.

