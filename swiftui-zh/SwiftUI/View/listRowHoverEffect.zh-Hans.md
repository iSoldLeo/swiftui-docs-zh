--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowHoverEffect(_:)

抓取时间：2025-11-30T21:24:52Z

---

# listRowHoverEffect(_:)

**实例方法**

请求包含列表行的悬停效果。

## 声明

```swift
nonisolated func listRowHoverEffect(_ effect: HoverEffect?) -> some View

```

## 参数

- **effect**：应用于整个列表行的悬停效果。

## 返回值

一个请求为包含列表行应用悬停效果的视图

## 讨论

默认情况下，VisionOS 中的列表行具有内置的悬停效果。在某些情况下，更改默认的悬停效果会很有用。

此修饰符可应用于列表行的内容，以请求将列表行的默认效果替换为提供的效果。如果视图未包含在 `List` 中，或者视图在此上下文中不支持悬停效果，则此修饰符无效。

使用 `nil` 效果指示不应修改列表行的默认悬停效果。

列表行不支持 [lift](../HoverEffect/lift.zh-Hans.md)。

## 配置交互

- **swipeActions(edge:allowsFullSwipe:content:)**：为列表中的行添加自定义滑动操作。

- **selectionDisabled(_:)**：添加一个条件，用于控制用户是否可以选择此视图。

- **listRowHoverEffectDisabled(_:)**：请求禁用包含列表行的悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowHoverEffect(_:)
crawled: 2025-11-30T21:24:52Z
---

# listRowHoverEffect(_:)

**Instance Method**

Requests that the containing list row use the provided hover effect.

## Declaration

```swift
nonisolated func listRowHoverEffect(_ effect: HoverEffect?) -> some View

```

## Parameters

- **effect**: The hover effect applied to the entire list row.

## Return Value

A view that requests a hover effect for a containing list row

## Discussion

By default, `List` rows have built-in hover effects in visionOS. In some cases, it is useful to change the default hover effect.

This modifier can be applied to a list row’s content to request that the list row’s default effect be replaced by the provided effect. If the view is not contained within a `List` or if the view does not support hover effects in this context, the modifier has no effect.

Use a `nil` effect to indicate that the list row’s default hover effect should not be modified.

[lift](../HoverEffect/lift.zh-Hans.md) is not supported for list rows.

## Configuring interaction

- **swipeActions(edge:allowsFullSwipe:content:)**: Adds custom swipe actions to a row in a list.
- **selectionDisabled(_:)**: Adds a condition that controls whether users can select this view.
- **listRowHoverEffectDisabled(_:)**: Requests that the containing list row have its hover effect disabled.

