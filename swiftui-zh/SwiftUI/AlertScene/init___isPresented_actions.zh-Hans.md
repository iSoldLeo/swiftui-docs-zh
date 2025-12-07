---
来源：https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:actions:)
抓取时间：2025-12-01T10:51:39Z
---

# init(_:isPresented:actions:)

**Initializer**

创建带有标题和动作集的警报场景。

### 声明

```swift
init(_ title: Text, isPresented: Binding<Bool>, @ViewBuilder actions: () -> Actions) where Message == EmptyView
```

## 参数

- **title**：警报标题。
- **isPresented**：与布尔值的绑定，决定是否显示警报。当用户按下或点击警报的某个操作时，系统会将此值设置为 `false` 并解除。
- **actions**：返回对话框操作的视图创建器。


---
source: https://developer.apple.com/documentation/SwiftUI/AlertScene/init(_:isPresented:actions:)
crawled: 2025-12-01T10:51:39Z
---

# init(_:isPresented:actions:)

**Initializer**

Creates an alert scene with a title and a set of actions.

## Declaration

```swift
init(_ title: Text, isPresented: Binding<Bool>, @ViewBuilder actions: () -> Actions) where Message == EmptyView
```

## Parameters

- **title**: The title of the alert.
- **isPresented**: A binding to a Boolean value that determines whether to present the alert. When the user presses or taps one of the alert’s actions, the system sets this value to `false` and dismisses.
- **actions**: A view builder returning the actions for the dialog.

