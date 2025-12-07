--- 来源：https://developer.apple.com/documentation/SwiftUI/FocusState

抓取时间：2025-12-02T17:04:42Z

---

# FocusState

**Structure**

一个属性包装器类型，可以读取和写入一个值，该值会随着场景中焦点位置的变化而更新。

## 声明

```swift
@frozen @propertyWrapper struct FocusState<Value> where Value : Hashable
```

## 概述

将此属性包装器与 [focused(_:equals:)](View/focused___equals.zh-Hans.md) 和 [focused(_:)](View/focused.zh-Hans.md) 结合使用，可以描述那些外观和内容与场景中焦点位置相关的视图。当焦点进入修改后的视图时，此属性的包装值会更新为与给定的原型值匹配。同样，当焦点离开时，此属性的包装值会重置为 `nil` 或 `false`。以编程方式设置属性值会产生相反的效果，使焦点移动到与更新值关联的视图。

在以下简单的登录屏幕示例中，当用户按下“登录”按钮且某个字段仍为空时，焦点会移动到该字段。否则，登录过程将继续进行。

```swift
struct LoginForm {
    enum Field: Hashable {
        case username
        case password
    }

    @State private var username = ""
    @State private var password = ""
    @FocusState private var focusedField: Field?

    var body: some View {
        Form {
            TextField("Username", text: $username)
                .focused($focusedField, equals: .username)

            SecureField("Password", text: $password)
                .focused($focusedField, equals: .password)

            Button("Sign In") {
                if username.isEmpty {
                    focusedField = .username
                } else if password.isEmpty {
                    focusedField = .password
                } else {
                    handleLogin(username, password)
                }
            }
        }
    }
}
```

为了允许视图树中完全没有焦点的情况，包装值必须是可选值或布尔值。根据需要将焦点绑定设置为 `false` 或 `nil`，以移除所有绑定字段的焦点。您还可以使用此方法移除 [TextField](TextField.zh-Hans.md) 的焦点，从而关闭键盘。

### 避免焦点绑定歧义

同一个视图可以有多个焦点绑定。在以下示例中，将 `focusedField` 设置为 `name` 或 `fullName` 都会导致该字段获得焦点：

```swift
struct ContentView: View {
    enum Field: Hashable {
        case name
        case fullName
    }
    @FocusState private var focusedField: Field?

    var body: some View {
        TextField("Full Name", ...)
            .focused($focusedField, equals: .name)
            .focused($focusedField, equals: .fullName)
    }
}
```

另一方面，将同一个值绑定到两个视图会产生歧义。在以下示例中，两个不同的字段都将焦点绑定到 `name` 值：

```swift
struct ContentView: View {
    enum Field: Hashable {
        case name
        case fullName
    }
    @FocusState private var focusedField: Field?

    var body: some View {
        TextField("Name", ...)
            .focused($focusedField, equals: .name)
        TextField("Full Name", ...)
            .focused($focusedField, equals: .name) // incorrect re-use of .name
    }
}
```

如果用户将焦点移动到任一字段，`focusedField` 绑定将更新为 `name`。但是，如果应用程序以编程方式将该值设置为 `name`，SwiftUI 会选择第一个候选值，在本例中是“名称”字段。在这种情况下，SwiftUI 还会发出运行时警告，因为重复绑定很可能是程序员的错误。

### 嵌套可聚焦视图

嵌套可聚焦视图中，[focused(_:equals:)](View/focused___equals.zh-Hans.md) 和 [focused(_:)](View/focused.zh-Hans.md) 之间的区别非常重要。

例如，考虑以下代码：

```swift
struct ContentView: View {
    @FocusState private var fieldIsFocused: Bool
    @FocusState private var containerIsFocused: Bool

    var body: some View {
        VStack {
            TextField("Name", ...)
                .focused($fieldIsFocused)
        }
        .focusable()
        .focused($containerIsFocused)
    }
}
```

上面的代码使用了 [focused(_:)](View/focused.zh-Hans.md)，它将焦点状态绑定到给定的布尔状态值。[focused(_:)](View/focused.zh-Hans.md) 会将 `containerIsFocused` 设置为 `true`，无论 `VStack` 本身获得焦点，还是仅当它包含的 `TextField` 获得焦点时，都会执行此操作。这种行为的出现是因为使用了两个独立的 `@FocusState` 实例来观察可聚焦视图 `VStack` 和 `TextField` 的焦点状态。当 `VStack` 没有焦点时，SwiftUI 会检查视图层级结构，找到焦点最近的视图来设置 `containerIsFocused` 的值。如果 `VStack` 中包含的 `TextField` 恰好获得了焦点，则 [focused(_:)](View/focused.zh-Hans.md) 会将 `containerIsFocused` 的值设置为 `true`。

如果需要观察是否只有 `VStack` 获得焦点，而其内部的 TextField 没有获得焦点，可以考虑使用 [focused(_:equals:)](View/focused___equals.zh-Hans.md) 来进行更精细的控制。

使用 [focused(_:equals:)](View/focused___equals.zh-Hans.md)，上述代码可以重写如下：

```swift
struct ContentView: View {
    enum Focus {
        case container
        case field
    }

    @FocusState private var focused: Focus?

    var body: some View {
        VStack {
            TextField("Name", ...)
                .focused($focused, equals: .field)
        }
        .focusable()
        .focused($focused, equals: .container)
    }
}
```

使用 [focused(_:equals:)](View/focused___equals.zh-Hans.md)，可以定义自定义数据结构来表示焦点状态。在这种情况下，使用了 `Focus` 枚举。它包含两个情况，一个用于表示可获得焦点的 `VStack`，另一个用于表示它包含的 `TextField`。 [focused(_:equals:)](View/focused___equals.zh-Hans.md) 仅当 `VStack` 自身获得焦点时才绑定到 `.container`，当 `TextField` 获得焦点时绑定到 `.field`。由于现在只有一个 `@FocusState` 属性，SwiftUI 能够区分 `VStack` *包含* 焦点和 *接收* 焦点这两种情况。

请注意，以上两种方法均可接受。[focused(_:equals:)](View/focused___equals.zh-Hans.md) 可用于观察给定视图当前是否接收焦点。而 [focused(_:)](View/focused.zh-Hans.md) 也可用于相同目的，此外，它还可以观察给定视图是否包含焦点。

## 创建焦点状态

- **init()**：创建一个绑定到布尔值的焦点状态。

## 检查焦点状态

- **projectedValue**：焦点状态值的投影，返回一个绑定。

- **FocusState.Binding**：一个属性包装类型，可以读取和写入指示当前焦点位置的值。

- **wrappedValue**：当前状态值，考虑了由于当前焦点位置而生效的任何绑定。

## 管理焦点状态

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改此视图。

- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。

- **isFocused**：返回最近的可聚焦祖先视图是否具有焦点。

- **FocusedValue**：用于观察当前聚焦视图或其祖先视图中值的属性包装器。

- **Entry()**：创建环境值、事务、容器值或聚焦值条目。

- **FocusedValueKey**：发布和观察聚焦值时使用的标识符类型协议。

- **FocusedBinding**：用于观察和自动解包当前聚焦视图或其祖先视图中的状态绑定的便捷属性包装器。

- **searchFocused(_:)**：通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定的布尔值来修改此视图。

- **searchFocused(_:equals:)**：通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定值来修改此视图。

## 符合以下规范

- DynamicProperty


---
source: https://developer.apple.com/documentation/SwiftUI/FocusState
crawled: 2025-12-02T17:04:42Z
---

# FocusState

**Structure**

A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.

## Declaration

```swift
@frozen @propertyWrapper struct FocusState<Value> where Value : Hashable
```

## Overview

Use this property wrapper in conjunction with [focused(_:equals:)](View/focused___equals.zh-Hans.md) and [focused(_:)](View/focused.zh-Hans.md) to describe views whose appearance and contents relate to the location of focus in the scene. When focus enters the modified view, the wrapped value of this property updates to match a given prototype value. Similarly, when focus leaves, the wrapped value of this property resets to `nil` or `false`. Setting the property’s value programmatically has the reverse effect, causing focus to move to the view associated with the updated value.

In the following example of a simple login screen, when the user presses the Sign In button and one of the fields is still empty, focus moves to that field. Otherwise, the sign-in process proceeds.

```swift
struct LoginForm {
    enum Field: Hashable {
        case username
        case password
    }

    @State private var username = ""
    @State private var password = ""
    @FocusState private var focusedField: Field?

    var body: some View {
        Form {
            TextField("Username", text: $username)
                .focused($focusedField, equals: .username)

            SecureField("Password", text: $password)
                .focused($focusedField, equals: .password)

            Button("Sign In") {
                if username.isEmpty {
                    focusedField = .username
                } else if password.isEmpty {
                    focusedField = .password
                } else {
                    handleLogin(username, password)
                }
            }
        }
    }
}
```

To allow for cases where focus is completely absent from a view tree, the wrapped value must be either an optional or a Boolean. Set the focus binding to `false` or `nil` as appropriate to remove focus from all bound fields. You can also use this to remove focus from a [TextField](TextField.zh-Hans.md) and thereby dismiss the keyboard.

### Avoid ambiguous focus bindings

The same view can have multiple focus bindings. In the following example, setting `focusedField` to either `name` or `fullName` causes the field to receive focus:

```swift
struct ContentView: View {
    enum Field: Hashable {
        case name
        case fullName
    }
    @FocusState private var focusedField: Field?

    var body: some View {
        TextField("Full Name", ...)
            .focused($focusedField, equals: .name)
            .focused($focusedField, equals: .fullName)
    }
}
```

On the other hand, binding the same value to two views is ambiguous. In the following example, two separate fields bind focus to the `name` value:

```swift
struct ContentView: View {
    enum Field: Hashable {
        case name
        case fullName
    }
    @FocusState private var focusedField: Field?

    var body: some View {
        TextField("Name", ...)
            .focused($focusedField, equals: .name)
        TextField("Full Name", ...)
            .focused($focusedField, equals: .name) // incorrect re-use of .name
    }
}
```

If the user moves focus to either field, the `focusedField` binding updates to `name`. However, if the app programmatically sets the value to `name`, SwiftUI chooses the first candidate, which in this case is the “Name” field. SwiftUI also emits a runtime warning in this case, since the repeated binding is likely a programmer error.

### Nest focusable views

It is important to consider the difference between [focused(_:equals:)](View/focused___equals.zh-Hans.md) and [focused(_:)](View/focused.zh-Hans.md) with nested focusable views.

For example, consider the following code:

```swift
struct ContentView: View {
    @FocusState private var fieldIsFocused: Bool
    @FocusState private var containerIsFocused: Bool

    var body: some View {
        VStack {
            TextField("Name", ...)
                .focused($fieldIsFocused)
        }
        .focusable()
        .focused($containerIsFocused)
    }
}
```

The code above uses [focused(_:)](View/focused.zh-Hans.md), which binds focus state to the given Boolean state value. [focused(_:)](View/focused.zh-Hans.md) sets `containerIsFocused` to `true` both when the `VStack` itself receives focus and *just* the `TextField` that it contains receives focus. This behavior occurs because two independent instances of `@FocusState` are used to observe the focus state of the focusable `VStack` and the `TextField`. When the `VStack` does not have focus, SwiftUI checks the view hierarchy to find the closest view with focus to set the value for `containerIsFocused`. If the `TextField` contained within this `VStack` happens to be focused, [focused(_:)](View/focused.zh-Hans.md) will set `containerIsFocused` to `true`.

If there is need to observe whether only the `VStack` has focus, but not the inner TextField, consider using [focused(_:equals:)](View/focused___equals.zh-Hans.md) instead, for more granular control.

With [focused(_:equals:)](View/focused___equals.zh-Hans.md), the above code can be rewritten as follows:

```swift
struct ContentView: View {
    enum Focus {
        case container
        case field
    }

    @FocusState private var focused: Focus?

    var body: some View {
        VStack {
            TextField("Name", ...)
                .focused($focused, equals: .field)
        }
        .focusable()
        .focused($focused, equals: .container)
    }
}
```

With [focused(_:equals:)](View/focused___equals.zh-Hans.md), it is possible to define a custom data structure to represent focus state. In this case, a `Focus` enumeration is used. It has two cases, one for the focusable `VStack` and another for the `TextField` it contains. [focused(_:equals:)](View/focused___equals.zh-Hans.md) binds focused to `.container` only when the `VStack` itself has focus, and to `.field` when the `TextField` has focus. Because now there is only one `@FocusState` property, SwiftUI is able to disambiguate between cases when `VStack` *contains* focus and *receives* focus itself.

Note that both of the above approaches are acceptable. [focused(_:equals:)](View/focused___equals.zh-Hans.md) can be used to observe whether the given view currently receives focus. While [focused(_:)](View/focused.zh-Hans.md) can be used for the same purpose, additionally it can observe whether the given view contains focus.

## Creating a focus state

- **init()**: Creates a focus state that binds to a Boolean.

## Inspecting the focus state

- **projectedValue**: A projection of the focus state value that returns a binding.
- **FocusState.Binding**: A property wrapper type that can read and write a value that indicates the current focus location.
- **wrappedValue**: The current state value, taking into account whatever bindings might be in effect due to the current location of focus.

## Managing focus state

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **FocusedValue**: A property wrapper for observing values from the focused view or one of its ancestors.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedValueKey**: A protocol for identifier types used when publishing and observing focused values.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

## Conforms To

- DynamicProperty

