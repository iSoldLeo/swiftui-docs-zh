---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationLink/isDetailLink(_:)
抓取时间： 2025-12-02T20:58:46Z
---

# isDetailLink(_:)

**实例方法**

设置导航链接，使其目标显示为包含导航视图的详细组件。

## 声明

```swift
func isDetailLink(_ isDetailLink: Bool) -> some View

```

## 参数

- **isDetailLink**：布尔值，用于指定在多栏导航视图中使用此链接时，是否将其目标显示为详细组件。

## 返回值

应用指定的详细链接行为的视图。

## 讨论

当导航链接在[NavigationSplitView](../NavigationSplitView.zh-Hans.md) 或多栏导航视图（如使用[ColumnNavigationViewStyle](../ColumnNavigationViewStyle.zh-Hans.md) 的视图）中使用时，该方法会设置相关行为。

例如，在双栏导航拆分视图中，如果`isDetailLink`是`true`，在侧边栏中触发链接会将详细栏的内容设置为链接的目标视图。如果`isDetailLink` 为`false`，则链接会导航到主栏中的目标视图。

如果不使用此方法设置详细链接行为，则默认行为为 `true`。

`isDetailLink`修饰符只影响视图目标链接。显示数据值的链接总是从包含该链接的列开始搜索匹配的导航目标。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationLink/isDetailLink(_:)
crawled: 2025-12-02T20:58:46Z
---

# isDetailLink(_:)

**Instance Method**

Sets the navigation link to present its destination as the detail component of the containing navigation view.

## Declaration

```swift
func isDetailLink(_ isDetailLink: Bool) -> some View

```

## Parameters

- **isDetailLink**: A Boolean value that specifies whether this link presents its destination as the detail component when used in a multi-column navigation view.

## Return Value

A view that applies the specified detail link behavior.

## Discussion

This method sets the behavior when the navigation link is used in a [NavigationSplitView](../NavigationSplitView.zh-Hans.md), or a multi-column navigation view, such as one using [ColumnNavigationViewStyle](../ColumnNavigationViewStyle.zh-Hans.md).

For example, in a two-column navigation split view, if `isDetailLink` is `true`, triggering the link in the sidebar column sets the contents of the detail column to be the link’s destination view. If `isDetailLink` is `false`, the link navigates to the destination view within the primary column.

If you do not set the detail link behavior with this method, the behavior defaults to `true`.

The `isDetailLink` modifier only affects view-destination links. Links that present data values always search for a matching navigation destination beginning in the column that contains the link.

