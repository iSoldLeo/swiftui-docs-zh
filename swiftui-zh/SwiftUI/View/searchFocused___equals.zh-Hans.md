--- 来源：https://developer.apple.com/documentation/SwiftUI/View/searchFocused(_:equals:)

抓取时间：2025-11-30T21:28:10Z

---

# searchFocused(_:equals:)

**实例方法**

通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定值来修改此视图。

## 声明

```swift
nonisolated func searchFocused<V>(_ binding: FocusState<V>.Binding, equals value: V) -> some View where V : Hashable

```

## 参数

- **binding**：要注册的状态绑定。当焦点移动到关联的搜索字段时，绑定会将绑定值设置为相应的匹配值。如果调用者以编程方式将状态值设置为匹配值，则焦点会移动到搜索字段。当焦点离开搜索字段时，绑定会将绑定值设置为 `nil`。如果调用者将值设置为 `nil`，SwiftUI 会自动取消焦点。

- **value**：用于确定是否应更改绑定时要匹配的值。

## 返回值

修改后的视图。

## 说明

要通过匹配简单的布尔条件来控制焦点，请改用 [searchFocused(_:)](searchFocused.zh-Hans.md) 修饰符。

有关使用可搜索修饰符的更多信息，请参阅 [Adding-a-search-interface-to-your-app](../Adding-a-search-interface-to-your-app.zh-Hans.md)。

## 管理焦点状态

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改此视图。

- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。

- **isFocused**：返回最近的可聚焦祖先是否具有焦点。

- **FocusState**：一种属性包装器类型，可以读取和写入 SwiftUI 会根据场景中焦点位置的变化而更新的值。

- **FocusedValue**：一种属性包装器，用于观察来自焦点视图或其父视图的值。

- **Entry()**：创建环境值、事务、容器值或焦点值条目。

- **FocusedValueKey**：发布和观察焦点值时使用的标识符类型协议。

- **FocusedBinding**：一种便捷的属性包装器，用于观察并自动解包来自焦点视图或其父视图的状态绑定。

- **searchFocused(_:)**：通过将与最近的可搜索修饰符关联的搜索字段的焦点状态绑定到给定的布尔值来修改此视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View/searchFocused(_:equals:)
crawled: 2025-11-30T21:28:10Z
---

# searchFocused(_:equals:)

**Instance Method**

Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

## Declaration

```swift
nonisolated func searchFocused<V>(_ binding: FocusState<V>.Binding, equals value: V) -> some View where V : Hashable

```

## Parameters

- **binding**: The state binding to register. When focus moves to the associated search field, the binding sets the bound value to the corresponding match value. If a caller sets the state value programmatically to the matching value, then focus moves to the search field. When focus leaves the search field, the binding sets the bound value to `nil`. If a caller sets the value to `nil`, SwiftUI automatically dismisses focus.
- **value**: The value to match against when determining whether the binding should change.

## Return Value

The modified view.

## Discussion

To control focus by matching a simple boolean condition, use the [searchFocused(_:)](searchFocused.zh-Hans.md) modifier instead.

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
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.

