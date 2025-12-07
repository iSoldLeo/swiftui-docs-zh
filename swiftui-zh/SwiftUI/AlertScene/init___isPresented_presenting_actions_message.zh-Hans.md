---
来源：https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:presenting:actions:message:)
抓取时间：2025-12-03T06:02:41Z


# init(_:isPresented:presenting:actions:message:)

**Initializer**

创建警报场景，使用给定的数据生成带有标题、操作集和消息的警报内容。请注意，这将代表您创建一个文本视图。

### 声明

```swift
init<S, T>(_ title: S, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> Actions, @ViewBuilder message: (T) -> Message) where S : StringProtocol
```

## 参数

- **title**：用作警报标题的文本字符串。
- **isPresented**：与布尔值的绑定，决定是否显示警报。当用户按下或点击警报的某个操作时，系统会将此值设为 `false` 并解除。
- **data**：传递给警报以填充信息和操作的真相源。
- **actions**：返回对话框操作的视图生成器。
- **message**：返回对话框操作的视图创建器：返回对话框信息的视图创建器。


---
source: https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:presenting:actions:message:)
crawled: 2025-12-03T06:02:41Z
---

# init(_:isPresented:presenting:actions:message:)

**Initializer**

Creates an alert scene, using the given data to produce the alert’s content with a title, a set of actions, and a message. Note that this creates a text view on your behalf.

## Declaration

```swift
init<S, T>(_ title: S, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> Actions, @ViewBuilder message: (T) -> Message) where S : StringProtocol
```

## Parameters

- **title**: A text string used as the title of the alert.
- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **data**: A source of truth that is passed to the alert to populate the message and actions.
- **actions**: A view builder returning the actions for the dialog.
- **message**: A view builder returning the message for the dialog.

