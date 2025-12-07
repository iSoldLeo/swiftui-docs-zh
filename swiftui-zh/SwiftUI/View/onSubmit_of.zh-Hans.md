--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onSubmit(of:_:)

抓取时间：2025-11-30T21:27:12Z

---

# onSubmit(of:_:)

**实例方法**

添加一个在用户向此视图提交值时要执行的操作。

## 声明

```swift
nonisolated func onSubmit(of triggers: SubmitTriggers = .text, _ action: @escaping () -> Void) -> some View

```

## 参数

- **triggers**：应触发所提供操作的触发器。

- **action**：提交值时要执行的操作。

## 说明

不同的视图可能具有不同的触发器来触发所提供操作。[TextField](../TextField.zh-Hans.md) 或 [SecureField](../SecureField.zh-Hans.md) 将在用户按下硬件或软件回车键时触发此操作。此修饰符还可以将此操作绑定到默认操作键盘快捷键。您可以针对单个视图或整个视图层次结构设置此操作。

```swift
TextField("Username", text: $username)
    .onSubmit {
        guard viewModel.validate() else { return }
        viewModel.login()
    }
```

您可以使用 [submitScope(_:)](submitScope.zh-Hans.md) 修饰符来阻止控件的提交触发器向上层视图层次结构传播到更高层的 `View.onSubmit(of:_:)` 修饰符。

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

您可以使用不同的提交触发器来筛选应调用所提供提交操作的触发器类型。例如，您可以提供值 [search](../SubmitTriggers/search.zh-Hans.md)，以便仅接收来自可搜索修饰符提供的搜索字段的提交触发器。

```swift
@StateObject private var viewModel = ViewModel()

NavigationView {
    SidebarView()
    DetailView()
}
.searchable(
    text: $viewModel.searchText,
    placement: .sidebar
) {
    SuggestionsView()
}
.onSubmit(of: .search) {
    viewModel.submitCurrentSearchQuery()
}
```

## 响应提交事件

- **submitScope(_:)**：防止源自此视图的提交触发器调用视图层次结构中更高层级提交修饰符配置的提交操作。

- **SubmitTriggers**：定义各种触发提交操作的触发器的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onSubmit(of:_:)
crawled: 2025-11-30T21:27:12Z
---

# onSubmit(of:_:)

**Instance Method**

Adds an action to perform when the user submits a value to this view.

## Declaration

```swift
nonisolated func onSubmit(of triggers: SubmitTriggers = .text, _ action: @escaping () -> Void) -> some View

```

## Parameters

- **triggers**: The triggers that should invoke the provided action.
- **action**: The action to perform on submission of a value.

## Discussion

Different views may have different triggers for the provided action. A [TextField](../TextField.zh-Hans.md), or [SecureField](../SecureField.zh-Hans.md) will trigger this action when the user hits the hardware or software return key. This modifier may also bind this action to a default action keyboard shortcut. You may set this action on an individual view or an entire view hierarchy.

```swift
TextField("Username", text: $username)
    .onSubmit {
        guard viewModel.validate() else { return }
        viewModel.login()
    }
```

You can use the [submitScope(_:)](submitScope.zh-Hans.md) modifier to stop a submit trigger from a control from propagating higher up in the view hierarchy to higher `View.onSubmit(of:_:)` modifiers.

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

You can use different submit triggers to filter the types of triggers that should invoke the provided submission action. For example, you may provide a value of [search](../SubmitTriggers/search.zh-Hans.md) to only hear submission triggers that originate from search fields vended by searchable modifiers.

```swift
@StateObject private var viewModel = ViewModel()

NavigationView {
    SidebarView()
    DetailView()
}
.searchable(
    text: $viewModel.searchText,
    placement: .sidebar
) {
    SuggestionsView()
}
.onSubmit(of: .search) {
    viewModel.submitCurrentSearchQuery()
}
```

## Responding to submission events

- **submitScope(_:)**: Prevents submission triggers originating from this view to invoke a submission action configured by a submission modifier higher up in the view hierarchy.
- **SubmitTriggers**: A type that defines various triggers that result in the firing of a submission action.

