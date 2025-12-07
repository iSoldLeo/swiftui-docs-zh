--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focused(_:equals:)

抓取时间：2025-12-02T17:43:01Z

---

# focused(_:equals:)

**实例方法**

通过将焦点状态绑定到给定的状态值来修改此视图。

## 声明

```swift
nonisolated func focused<Value>(_ binding: FocusState<Value>.Binding, equals value: Value) -> some View where Value : Hashable

```

## 参数

- **binding**：要注册的状态绑定。当焦点移动到修改后的视图时，绑定会将绑定值设置为相应的匹配值。如果调用者以编程方式将状态值设置为匹配值，则焦点会移动到修改后的视图。当焦点离开修改后的视图时，绑定会将绑定值设置为 `nil`。如果调用者将值设置为 `nil`，SwiftUI 会自动取消焦点。

- **value**：用于确定绑定是否应更改时要匹配的值。

## 返回值

修改后的视图。

## 说明

使用此修饰符可使视图在 `binding` 等于 `value` 时获得焦点。通常，您可以创建一个可能获得焦点的字段枚举，绑定此枚举的一个实例，并将其 case 分配给可聚焦的视图。

以下示例使用 `LoginForm` 枚举的 case 来绑定两个 [TextField](../TextField.zh-Hans.md) 视图的焦点状态。登录按钮会验证字段，并将绑定的 `focusedField` 值设置为任何需要用户更正问题的字段。 ```swift
struct LoginForm {
    enum Field: Hashable {
        case usernameField
        case passwordField
    }

    @State private var username = ""
    @State private var password = ""
    @FocusState private var focusedField: Field?

    var body: some View {
        Form {
            TextField("Username", text: $username)
                .focused($focusedField, equals: .usernameField)

            SecureField("Password", text: $password)
                .focused($focusedField, equals: .passwordField)

            Button("Sign In") {
                if username.isEmpty {
                    focusedField = .usernameField
                } else if password.isEmpty {
                    focusedField = .passwordField
                } else {
                    handleLogin(username, password)
                }
            }
        }
    }
}
```

要使用布尔值控制焦点，请改用 [focused(_:)](focused.zh-Hans.md) 方法。

## 管理焦点状态

- **focused(_:)**：通过将焦点状态绑定到给定的布尔值来修改此视图。

- **isFocused**：返回最近的可聚焦祖先视图是否具有焦点。

- **FocusState**：一种属性包装器类型，可以读取和写入 SwiftUI 会随着场景中焦点位置的变化而更新的值。

- **FocusedValue**：一种用于观察焦点视图或其祖先视图中值的属性包装器。

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **FocusedValueKey**：用于发布和观察聚焦值的标识符类型的协议。

- **FocusedBinding**：用于观察和自动解包聚焦视图或其祖先视图的状态绑定的便捷属性包装器。

- **searchFocused(_:)**：通过将与最近的可搜索修饰符关联的搜索字段的聚焦状态绑定到给定的布尔值来修改此视图。

- **searchFocused(_:equals:)**：通过将与最近的可搜索修饰符关联的搜索字段的聚焦状态绑定到给定的值来修改此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focused(_:equals:)
crawled: 2025-12-02T17:43:01Z
---

# focused(_:equals:)

**Instance Method**

Modifies this view by binding its focus state to the given state value.

## Declaration

```swift
nonisolated func focused<Value>(_ binding: FocusState<Value>.Binding, equals value: Value) -> some View where Value : Hashable

```

## Parameters

- **binding**: The state binding to register. When focus moves to the modified view, the binding sets the bound value to the corresponding match value. If a caller sets the state value programmatically to the matching value, then focus moves to the modified view. When focus leaves the modified view, the binding sets the bound value to `nil`. If a caller sets the value to `nil`, SwiftUI automatically dismisses focus.
- **value**: The value to match against when determining whether the binding should change.

## Return Value

The modified view.

## Discussion

Use this modifier to cause the view to receive focus whenever the `binding` equals the `value`. Typically, you create an enumeration of fields that may receive focus, bind an instance of this enumeration, and assign its cases to focusable views.

The following example uses the cases of a `LoginForm` enumeration to bind the focus state of two [TextField](../TextField.zh-Hans.md) views. A sign-in button validates the fields and sets the bound `focusedField` value to any field that requires the user to correct a problem.

```swift
struct LoginForm {
    enum Field: Hashable {
        case usernameField
        case passwordField
    }

    @State private var username = ""
    @State private var password = ""
    @FocusState private var focusedField: Field?

    var body: some View {
        Form {
            TextField("Username", text: $username)
                .focused($focusedField, equals: .usernameField)

            SecureField("Password", text: $password)
                .focused($focusedField, equals: .passwordField)

            Button("Sign In") {
                if username.isEmpty {
                    focusedField = .usernameField
                } else if password.isEmpty {
                    focusedField = .passwordField
                } else {
                    handleLogin(username, password)
                }
            }
        }
    }
}
```

To control focus using a Boolean, use the [focused(_:)](focused.zh-Hans.md) method instead.

## Managing focus state

- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **FocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.
- **FocusedValue**: A property wrapper for observing values from the focused view or one of its ancestors.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedValueKey**: A protocol for identifier types used when publishing and observing focused values.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

