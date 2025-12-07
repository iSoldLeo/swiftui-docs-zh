---
来源： https://developer.apple.com/documentation/SwiftUI/FocusedValue
抓取时间： 2025-12-02T17:43:04Z
---

# FocusedValue

**Structure**

属性包装器，用于观察焦点视图或其某个祖先视图中的值。

## 声明

```swift
@propertyWrapper struct FocusedValue<Value>
```

## 概览

如果多个视图使用相同的键发布值，包装后的属性将反映最靠近焦点的视图的值。

## 创建值

- **init(_:)**：为给定的键路径创建一个新的属性包装器。

## 获取值

- **wrappedValue**：在当前视图层次结构的范围和状态下，焦点键的值。

## 管理焦点状态

- **focused(_:equals:)**：通过将焦点状态绑定到给定的状态值来修改该视图。
- **focused(_:)**：通过将焦点状态绑定到给定的布尔状态值来修改此视图。
- **isFocused**：返回最近的可聚焦祖先是否已聚焦。
- **FocusState**：一种属性包装器类型，可以读写一个值，当场景中焦点的位置发生变化时，SwiftUI 会更新该值。
- **Entry()**：创建环境值、事务、容器值或焦点值条目。
- **FocusedValueKey**：发布和观察重点值时使用的标识符类型协议。
- **FocusedBinding**：方便的属性包装器，用于观察和自动解除来自焦点视图或其祖先之一的状态绑定。
- **searchFocused(_:)**：通过将与最近的可搜索修改器相关联的搜索字段的焦点状态绑定到给定的布尔值来修改此视图。
- **searchFocused(_:equals:)**：通过将与最近的可搜索修改器相关联的搜索字段的焦点状态绑定到给定值来修改此视图。

## 符合

- 动态属性


---
source: https://developer.apple.com/documentation/SwiftUI/FocusedValue
crawled: 2025-12-02T17:43:04Z
---

# FocusedValue

**Structure**

A property wrapper for observing values from the focused view or one of its ancestors.

## Declaration

```swift
@propertyWrapper struct FocusedValue<Value>
```

## Overview

If multiple views publish values using the same key, the wrapped property will reflect the value from the view closest to focus.

## Creating the value

- **init(_:)**: A new property wrapper for the given key path.

## Getting the value

- **wrappedValue**: The value for the focus key given the current scope and state of the focused view hierarchy.

## Managing focus state

- **focused(_:equals:)**: Modifies this view by binding its focus state to the given state value.
- **focused(_:)**: Modifies this view by binding its focus state to the given Boolean state value.
- **isFocused**: Returns whether the nearest focusable ancestor has focus.
- **FocusState**: A property wrapper type that can read and write a value that SwiftUI updates as the placement of focus within the scene changes.
- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.
- **FocusedValueKey**: A protocol for identifier types used when publishing and observing focused values.
- **FocusedBinding**: A convenience property wrapper for observing and automatically unwrapping state bindings from the focused view or one of its ancestors.
- **searchFocused(_:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given Boolean value.
- **searchFocused(_:equals:)**: Modifies this view by binding the focus state of the search field associated with the nearest searchable modifier to the given value.

## Conforms To

- DynamicProperty

