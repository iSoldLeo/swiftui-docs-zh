--- 来源：https://developer.apple.com/documentation/swiftui/view/layoutdirectionbehavior(_:)

抓取时间：2025-12-03T06:37:20Z

---

# layoutDirectionBehavior(_:)

**实例方法**

设置此视图在不同布局方向上的行为。

## 声明

```swift
nonisolated func layoutDirectionBehavior(_ behavior: LayoutDirectionBehavior) -> some View

```

## 参数

- **behavior**：一个 LayoutDirectionBehavior 值，指示此视图是否应在特定布局方向上镜像。默认情况下，视图会在从右到左的上下文中自动调整其布局，无需镜像。

## 返回值

一个根据给定布局方向有条件地水平镜像其内容的视图。

## 讨论

当需要在布局方向上呈现视图内容时，使用 `layoutDirectionBehavior(_:)` 来使系统水平镜像视图内容。

要覆盖特定视图的布局方向，请使用 [environment(_:_:)](environment.zh-Hans.md) 视图修饰符来显式覆盖该视图的 [layoutDirection](../EnvironmentValues/layoutDirection.zh-Hans.md) 环境值。

## 设置布局方向

- **LayoutDirectionBehavior**：描述布局方向更改时应发生的情况。

- **layoutDirection**：与当前环境关联的布局方向。

- **LayoutDirection**：SwiftUI 可以布局内容的方向。

- **LayoutRotationUnaryLayout**


---
source: https://developer.apple.com/documentation/swiftui/view/layoutdirectionbehavior(_:)
crawled: 2025-12-03T06:37:20Z
---

# layoutDirectionBehavior(_:)

**Instance Method**

Sets the behavior of this view for different layout directions.

## Declaration

```swift
nonisolated func layoutDirectionBehavior(_ behavior: LayoutDirectionBehavior) -> some View

```

## Parameters

- **behavior**: A LayoutDirectionBehavior value that indicates whether this view should mirror in a particular layout direction. By default, views will adjust their layouts automatically in a right-to-left context and do not need to be mirrored.

## Return Value

A view that conditionally mirrors its contents horizontally in a given layout direction.

## Discussion

Use `layoutDirectionBehavior(_:)` when you need the system to horizontally mirror the contents of the view when presented in a layout direction.

To override the layout direction for a specific view, use the [environment(_:_:)](environment.zh-Hans.md) view modifier to explicitly override the [layoutDirection](../EnvironmentValues/layoutDirection.zh-Hans.md) environment value for the view.

## Setting a layout direction

- **LayoutDirectionBehavior**: A description of what should happen when the layout direction changes.
- **layoutDirection**: The layout direction associated with the current environment.
- **LayoutDirection**: A direction in which SwiftUI can lay out content.
- **LayoutRotationUnaryLayout**

