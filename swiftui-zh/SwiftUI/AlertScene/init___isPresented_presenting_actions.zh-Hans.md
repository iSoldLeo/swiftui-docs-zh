---
来源：https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:presenting:actions:)
抓取时间：2025-12-03T06:02:41Z
---

# init(_:isPresented:presenting:actions:)

**Initializer**

创建警报场景，使用给定的数据生成带有标题和操作集的警报内容。请注意，这将代表您创建一个文本视图。

### 声明

```swift
init<S, T>(_ title: S, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> Actions) where Message == EmptyView, S : StringProtocol
```

## 参数

- **title**：警报标题。
- **isPresented**：与布尔值的绑定，决定是否显示警报。当用户按下或点击警报的某个操作时，系统会将此值设为 `false` 并解除。
- **data**：传递给警报以填充信息和操作的真相源。
- **actions**：返回对话框操作的视图生成器。


---
source: https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:presenting:actions:)
crawled: 2025-12-03T06:02:41Z
---

# init(_:isPresented:presenting:actions:)

**Initializer**

Creates an alert scene, using the given data to produce the alert’s content with a title, and a set of actions. Note that this creates a text view on your behalf.

## Declaration

```swift
init<S, T>(_ title: S, isPresented: Binding<Bool>, presenting data: T?, @ViewBuilder actions: (T) -> Actions) where Message == EmptyView, S : StringProtocol
```

## Parameters

- **title**: The title of the alert.
- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **data**: A source of truth that is passed to the alert to populate the message and actions.
- **actions**: A view builder returning the actions for the dialog.

