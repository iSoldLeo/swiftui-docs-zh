--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focused(_:)

抓取时间：2025-12-02T17:43:02Z

---

# focused(_:)

**实例方法**

通过将焦点状态绑定到给定的布尔值来修改此视图。

## 声明

```swift
nonisolated func focused(_ condition: FocusState<Bool>.Binding) -> some View

```

## 参数

- **condition**：要绑定的焦点状态。当焦点移动到视图时，绑定会将绑定值设置为 `true`。如果调用者以编程方式将该值设置为 `true`，则焦点会移动到修改后的视图。当焦点离开修改后的视图时，绑定会将该值设置为 `false`。如果调用者将值设置为 `false`，SwiftUI 会自动取消焦点。

## 返回值

修改后的视图。

## 说明

使用此修饰符可使视图在 `condition` 的值为 `true` 时获得焦点。您可以使用此修饰符来观察单个视图的焦点状态，或以编程方式设置和移除视图的焦点。

在以下示例中，单个 [TextField](../TextField.zh-Hans.md) 接受用户所需的 `username`。文本字段将其焦点状态绑定到布尔值 `usernameFieldIsFocused`。“提交”按钮的操作会验证名称是否可用。如果名称不可用，按钮会将 `usernameFieldIsFocused` 设置为 `true`，使焦点返回文本字段，以便用户可以输入其他名称。

```swift
@State private var username: String = ""
@FocusState private var usernameFieldIsFocused: Bool
@State private var showUsernameTaken = false

var body: some View {
    VStack {
        TextField("Choose a username.", text: $username)
            .focused($usernameFieldIsFocused)
        if showUsernameTaken {
            Text("That username is taken. Please choose another.")
        }
        Button("Submit") {
            showUsernameTaken = false
            if !isUserNameAvailable(username: username) {
                usernameFieldIsFocused = true
                showUsernameTaken = true
            }
        }
    }
}
```

要通过匹配值来控制焦点，请改用 [focused(_:equals:)](focused___equals.zh-Hans.md) 方法。

## 管理焦点状态

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改此视图。

- **isFocused**：返回最近的可聚焦祖先元素是否具有焦点。

- **FocusState**：一种属性包装类型，可以读取和写入 SwiftUI 会随着场景中焦点位置的变化而更新的值。

- **FocusedValue**：用于观察当前聚焦视图或其父视图中值的属性包装器。

- **Entry()**：创建环境值、事务值、容器值或聚焦值条目。

- **FocusedValueKey**：发布和观察聚焦值时使用的标识符类型协议。

- **FocusedBinding**：用于观察并自动解包当前聚焦视图或其父视图中的状态绑定的便捷属性包装器。

- **searchFocused(_:)**：通过将与最近的可搜索修饰符关联的搜索字段的聚焦状态绑定到给定的布尔值来修改此视图。

- **searchFocused(_:equals:)**：通过将与最近的可搜索修饰符关联的搜索字段的聚焦状态绑定到给定的值来修改此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focused(_:)
crawled: 2025-12-02T17:43:02Z
---

# focused(_:)

**Instance Method**

Modifies this view by binding its focus state to the given Boolean state value.

## Declaration

```swift
nonisolated func focused(_ condition: FocusState<Bool>.Binding) -> some View

```

## Parameters

- **condition**: The focus state to bind. When focus moves to the view, the binding sets the bound value to `true`. If a caller sets the value to  `true` programmatically, then focus moves to the modified view. When focus leaves the modified view, the binding sets the value to `false`. If a caller sets the value to `false`, SwiftUI automatically dismisses focus.

## Return Value

The modified view.

## Discussion

Use this modifier to cause the view to receive focus whenever the `condition` value is `true`. You can use this modifier to observe the focus state of a single view, or programmatically set and remove focus from the view.

In the following example, a single [TextField](../TextField.zh-Hans.md) accepts a user’s desired `username`. The text field binds its focus state to the Boolean value `usernameFieldIsFocused`. A “Submit” button’s action verifies whether the name is available. If the name is unavailable, the button sets `usernameFieldIsFocused` to `true`, which causes focus to return to the text field, so the user can enter a different name.

```swift
@State private var username: String = ""
@FocusState private var usernameFieldIsFocused: Bool
@State private var showUsernameTaken = false

var body: some View {
    VStack {
        TextField("Choose a username.", text: $username)
            .focused($usernameFieldIsFocused)
        if showUsernameTaken {
            Text("That username is taken. Please choose another.")
        }
        Button("Submit") {
            showUsernameTaken = false
            if !isUserNameAvailable(username: username) {
                usernameFieldIsFocused = true
                showUsernameTaken = true
            }
        }
    }
}
```

To control focus by matching a value, use the [focused(_:equals:)](focused___equals.zh-Hans.md) method instead.

## Managing focus state

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **FocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.
- **FocusedValue**: A property wrapper for observing values from the focused view or one of its ancestors.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedValueKey**: A protocol for identifier types used when publishing and observing focused values.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

