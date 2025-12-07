---
来源： https://developer.apple.com/documentation/swiftui/focusedvaluekey
抓取时间： 2025-12-04T13:39:27Z
---

# FocusedValueKey

**Protocol**

在发布和观察聚焦值时使用的标识符类型协议。

### 声明

```swift
protocol FocusedValueKey
```

## 概览

与 [EnvironmentKey](EnvironmentKey.zh-Hans.md) 不同，`FocusedValueKey` 没有缺省值要求，因为键的缺省值总是 `nil`。

使用`Entry` 宏，通过用新属性扩展`FocusedValues` 来创建自定义的重点值：

```swift
extension FocusedValues {
    @Entry var selectedItem: Item?
}
```

另外，也可以通过手动创建符合本协议的类型来创建重点值键：

```swift
struct SelectedItemKey: FocusedValueKey {
    typealias Value = Item
}
```

然后扩展[FocusedValues](FocusedValues.zh-Hans.md)，为你的键添加一个计算属性：

```swift
extension FocusedValues {
    var selectedItem: Item? {
        get { self[SelectedItemKey.self] }
        set { self[SelectedItemKey.self] = newValue }
    }
}
```

## 指定值类型

- **Value**

## 管理焦点状态

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改此视图。
- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。
- **isFocused**：返回最近的可聚焦祖先是否已聚焦。
- **FocusState**：一种属性包装器类型，可以读写一个值，当场景中焦点的位置发生变化时，SwiftUI 会更新该值。
- **FocusedValue**：一个属性包装器，用于观察焦点视图或其某个祖先视图中的值。
- **Entry()**：创建环境值、事务、容器值或焦点值条目。
- **FocusedBinding**：方便的属性包装器，用于观察和自动解除来自焦点视图或其祖先之一的状态绑定。
- **searchFocused(_:)**：通过将与最近的可搜索修改器相关联的搜索字段的焦点状态绑定到给定的布尔值来修改该视图。
- **searchFocused(_:equals:)**：通过将与最近的可搜索修改器相关联的搜索字段的焦点状态绑定为给定值来修改此视图。


---
source: https://developer.apple.com/documentation/swiftui/focusedvaluekey
crawled: 2025-12-04T13:39:27Z
---

# FocusedValueKey

**Protocol**

A protocol for identifier types used when publishing and observing focused values.

## Declaration

```swift
protocol FocusedValueKey
```

## Overview

Unlike [EnvironmentKey](EnvironmentKey.zh-Hans.md), `FocusedValueKey` has no default value requirement, because the default value for a key is always `nil`.

Use the `Entry` macro to create custom focused values by extending `FocusedValues` with new properties:

```swift
extension FocusedValues {
    @Entry var selectedItem: Item?
}
```

Alternatively it is possible to create a focused value key by manually creating a type that conforms to this protocol:

```swift
struct SelectedItemKey: FocusedValueKey {
    typealias Value = Item
}
```

Then extend [FocusedValues](FocusedValues.zh-Hans.md) to add a computed property for your key:

```swift
extension FocusedValues {
    var selectedItem: Item? {
        get { self[SelectedItemKey.self] }
        set { self[SelectedItemKey.self] = newValue }
    }
}
```

## Specifying the value type

- **Value**

## Managing focus state

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **FocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.
- **FocusedValue**: A property wrapper for observing values from the focused view or one of its ancestors.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

