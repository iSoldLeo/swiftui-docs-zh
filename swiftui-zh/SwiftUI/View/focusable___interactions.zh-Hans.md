--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusable(_:interactions:)

抓取时间：2025-12-02T17:42:59Z

---

# focusable(_:interactions:)

**实例方法**

指定视图是否可聚焦，如果可聚焦，则指定它支持哪些焦点驱动的交互方式。

## 声明

```swift
nonisolated func focusable(_ isFocusable: Bool = true, interactions: FocusInteractions) -> some View

```

## 参数

- **isFocusable**：`true` 表示视图是否参与焦点；`false` 表示不参与焦点。默认值为 `true`。

- **interactions**：视图支持的焦点交互类型。默认值为 `.automatic`。

## 返回值

一个用于设置其子视图是否可聚焦的视图。

## 说明

默认情况下，SwiftUI 启用所有可能的焦点交互。然而，在 macOS 和 iOS 系统中，按钮类视图通常仅在用户于“设置”应用中启用系统级键盘导航后才接受焦点。客户端可以通过仅支持 `.activate` 交互，在自定义视图中重现此行为。

```swift
MyTapGestureView(...)
    .focusable(interactions: .activate)
```

## 指示视图是否可以接收焦点

- **focusable(_:)**：指定视图是否可聚焦。

- **FocusInteractions**：这些值描述了视图可以支持的不同焦点交互。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusable(_:interactions:)
crawled: 2025-12-02T17:42:59Z
---

# focusable(_:interactions:)

**Instance Method**

Specifies if the view is focusable, and if so, what focus-driven interactions it supports.

## Declaration

```swift
nonisolated func focusable(_ isFocusable: Bool = true, interactions: FocusInteractions) -> some View

```

## Parameters

- **isFocusable**: `true` if the view should participate in focus; `false` otherwise. The default value is `true`.
- **interactions**: The types of focus interactions supported by the view. The default value is `.automatic`.

## Return Value

A view that sets whether its child is focusable.

## Discussion

By default, SwiftUI enables all possible focus interactions. However, on macOS and iOS it is conventional for button-like views to only accept focus when the user has enabled keyboard navigation system-wide in the Settings app. Clients can reproduce this behavior with custom views by only supporting `.activate` interactions.

```swift
MyTapGestureView(...)
    .focusable(interactions: .activate)
```



## Indicating that a view can receive focus

- **focusable(_:)**: Specifies if the view is focusable.
- **FocusInteractions**: Values describe different focus interactions that a view can support.

