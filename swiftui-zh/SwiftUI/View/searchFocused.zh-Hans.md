--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchFocused(_:)

抓取时间：2025-11-30T21:28:09Z

---

# searchFocused(_:)

**实例方法**

通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定的布尔值来修改此视图。

## 声明

```swift
nonisolated func searchFocused(_ binding: FocusState<Bool>.Binding) -> some View

```

## 返回值

修改后的视图。

## 说明

要通过匹配非布尔值来控制焦点，请改用 [searchFocused(_:equals:)](searchFocused___equals.zh-Hans.md) 修饰符。

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 管理焦点状态

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改此视图。

- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。

- **isFocused**：返回最近的可聚焦祖先是否拥有焦点。

- **FocusState**：一种属性包装类型，可以读取和写入 SwiftUI 会随着场景中焦点位置的变化而更新的值。

- **FocusedValue**：一种用于观察焦点视图或其祖先视图中值的属性包装类型。

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **FocusedValueKey**：用于发布和观察焦点值时使用的标识符类型的协议。 - **FocusedBinding**：一个便捷的属性包装器，用于观察并自动解包当前聚焦视图或其父视图的状态绑定。

- **searchFocused(_:equals:)**：通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定值来修改此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchFocused(_:)
crawled: 2025-11-30T21:28:09Z
---

# searchFocused(_:)

**Instance Method**

Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.

## Declaration

```swift
nonisolated func searchFocused(_ binding: FocusState<Bool>.Binding) -> some View

```

## Return Value

The modified view.

## Discussion

To control focus by matching a non-boolean value, use the [searchFocused(_:equals:)](searchFocused___equals.zh-Hans.md) modifier instead.

For more information about using searchable modifiers, refer to [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md).

## Managing focus state

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **FocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.
- **FocusedValue**: A property wrapper for observing values from the focused view or one of its ancestors.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedValueKey**: A protocol for identifier types used when publishing and observing focused values.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

