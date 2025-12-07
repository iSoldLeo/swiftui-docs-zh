--- 来源：https://developer.apple.com/documentation/SwiftUI/View/submitScope(_:)

抓取时间：2025-11-30T21:27:13Z

---

# submitScope(_:)

**实例方法**

阻止此视图发起的提交触发器调用视图层级结构中更高层级提交修饰符配置的提交操作。

## 声明

```swift
nonisolated func submitScope(_ isBlocking: Bool = true) -> some View

```

## 参数

- **isBlocking**：一个布尔值，指示此作用域是否主动阻止提交触发器到达更高层级的提交操作。

## 说明

当您希望避免特定视图发起由 [onSubmit(of:_:)](onSubmit_of.zh-Hans.md) 修饰符配置的提交操作时，请使用此修饰符。在以下示例中，标签字段不会触发表单提交：

```swift
Form {
    TextField("Username", text: $viewModel.userName)
    SecureField("Password", text: $viewModel.password)

    TextField("Tags", text: $viewModel.tags)
        .submitScope()
}
.onSubmit {
    guard viewModel.validate() else { return }
    viewModel.login()
}
```

## 响应提交事件

- **onSubmit(of:_:)**：添加用户向此视图提交值时要执行的操作。

- **SubmitTriggers**：定义各种触发器的类型，这些触发器会导致提交操作的触发。


---
source: https://developer.apple.com/documentation/SwiftUI/View/submitScope(_:)
crawled: 2025-11-30T21:27:13Z
---

# submitScope(_:)

**Instance Method**

Prevents submission triggers originating from this view to invoke a submission action configured by a submission modifier higher up in the view hierarchy.

## Declaration

```swift
nonisolated func submitScope(_ isBlocking: Bool = true) -> some View

```

## Parameters

- **isBlocking**: A Boolean that indicates whether this scope is actively blocking submission triggers from reaching higher submission actions.

## Discussion

Use this modifier when you want to avoid specific views from initiating a submission action configured by the [onSubmit(of:_:)](onSubmit_of.zh-Hans.md) modifier. In the example below, the tag field doesn’t trigger the submission of the form:

```swift
Form {
    TextField("Username", text: $viewModel.userName)
    SecureField("Password", text: $viewModel.password)

    TextField("Tags", text: $viewModel.tags)
        .submitScope()
}
.onSubmit {
    guard viewModel.validate() else { return }
    viewModel.login()
}
```

## Responding to submission events

- **onSubmit(of:_:)**: Adds an action to perform when the user submits a value to this view.
- **SubmitTriggers**: A type that defines various triggers that result in the firing of a submission action.

