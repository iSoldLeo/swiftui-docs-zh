---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isFocused
抓取时间： 2025-12-02T17:43:03Z
---

# isFocused

**实例属性**

返回最近的可聚焦祖先是否已聚焦。

## 声明

```swift
var isFocused: Bool { get }
```

## 讨论

如果没有可聚焦的祖先，则值`false`。

## 管理焦点状态

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改此视图。
- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。
- **FocusState**：一种属性包装器类型，可以读写一个值，当场景中焦点位置发生变化时，SwiftUI 会更新该值。
- **FocusedValue**：用于观察焦点视图或其祖先之一的值的属性包装器。
- **Entry()**：创建环境值、事务、容器值或焦点值条目。
- **FocusedValueKey**：发布和观察重点值时使用的标识符类型协议。
- **FocusedBinding**：方便的属性包装器，用于观察和自动解除来自聚焦视图或其祖先之一的状态绑定。
- **searchFocused(_:)**：通过将与最近的可搜索修改器相关联的搜索字段的焦点状态绑定到给定的布尔值来修改此视图。
- **searchFocused(_:equals:)**：通过将与最近的可搜索修改器相关联的搜索字段的焦点状态绑定到给定值来修改此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/isFocused
crawled: 2025-12-02T17:43:03Z
---

# isFocused

**Instance Property**

Returns whether the nearest focusable ancestor has focus.

## Declaration

```swift
var isFocused: Bool { get }
```

## Discussion

If there is no focusable ancestor, the value is `false`.

## Managing focus state

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **FocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.
- **FocusedValue**: A property wrapper for observing values from the focused view or one of its ancestors.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedValueKey**: A protocol for identifier types used when publishing and observing focused values.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

