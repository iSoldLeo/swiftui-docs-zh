--- 来源：https://developer.apple.com/documentation/SwiftUI/View/listRowHoverEffectDisabled(_:)

抓取时间：2025-11-30T21:24:53Z

---

# listRowHoverEffectDisabled(_:)

**实例方法**

请求禁用包含列表行的悬停效果。

## 声明

```swift
nonisolated func listRowHoverEffectDisabled(_ disabled: Bool = true) -> some View

```

## 参数

- **disabled**：一个布尔值，用于确定包含列表行是否应显示其默认悬停效果。

## 返回值

一个视图，该视图请求有条件地禁用其包含列表行的默认悬停效果。

## 说明

默认情况下，VisionOS 中的行具有内置的悬停效果。在某些情况下，禁用默认悬停效果会很有用。

## 配置交互

- **swipeActions(edge:allowsFullSwipe:content:)**：为列表中的某一行添加自定义滑动操作。

- **selectionDisabled(_:)**：添加一个条件，用于控制用户是否可以选择此视图。

- **listRowHoverEffect(_:)**：请求包含该行的列表行使用提供的悬停效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View/listRowHoverEffectDisabled(_:)
crawled: 2025-11-30T21:24:53Z
---

# listRowHoverEffectDisabled(_:)

**Instance Method**

Requests that the containing list row have its hover effect disabled.

## Declaration

```swift
nonisolated func listRowHoverEffectDisabled(_ disabled: Bool = true) -> some View

```

## Parameters

- **disabled**: A Boolean value that determines whether the containing list row should display its default hover effect.

## Return Value

A view that requests the default hover effect on its containing list row to conditionally be disabled.

## Discussion

By default, `List` rows have built-in hover effects in visionOS. In some cases, it is useful to disable the default hover effect.

## Configuring interaction

- **swipeActions(edge:allowsFullSwipe:content:)**: Adds custom swipe actions to a row in a list.
- **selectionDisabled(_:)**: Adds a condition that controls whether users can select this view.
- **listRowHoverEffect(_:)**: Requests that the containing list row use the provided hover effect.

