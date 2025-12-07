--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onScrollPhaseChange(_:)

抓取时间：2025-11-30T21:25:36Z

---

# onScrollPhaseChange(_:)

**实例方法**

添加一个操作，当层级结构中第一个滚动视图的滚动阶段发生变化时执行。

## 声明

```swift
nonisolated func onScrollPhaseChange(_ action: @escaping (ScrollPhase, ScrollPhase) -> Void) -> some View

```

## 参数

- **action**：当滚动阶段发生变化时要运行的闭包。

## 说明

使用此修饰符可以获知滚动视图的滚动阶段变化。滚动视图可能处于各种不同的滚动阶段，例如平移或减速。有关滚动视图滚动阶段的更多信息，请参阅 [ScrollPhase](../ScrollPhase.zh-Hans.md)。

当滚动视图的阶段发生变化时，系统会调用您提供的操作。在以下示例中，当滚动视图过渡到 [decelerating](../ScrollPhase/decelerating.zh-Hans.md) 或 [idle](../ScrollPhase/idle.zh-Hans.md) 阶段时，选择绑定会更新。

```swift
@Binding var selection: SelectionValue?

ScrollView {
    // ...
}
.onScrollPhaseChange { _, newPhase in
    if newPhase == .decelerating || newPhase == .idle {
        selection = updateSelection()
    }
}
```

系统还可以提供滚动视图在阶段变化时的几何形状。您可以利用几何形状来了解滚动视图在阶段变化之间移动的位置，并根据该信息更新相关状态。在以下示例中，工具栏内容是否隐藏取决于用户上次滚动的方向。

```swift
@Binding var hidesToolbarContent: Bool
@State private var lastOffset: CGFloat = 0.0

ScrollView {
    // ...
}
.onScrollPhaseChange { oldPhase, newPhase, context in
    if newPhase == .interacting {
        lastOffset = context.geometry.contentOffset.y
    }
    if oldPhase == .interacting, newPhase != .animating,
        context.geometry.contentOffset.y - lastOffset < 0.0
    {
        hidesToolbarContent = true
    } else {
        hidesToolbarContent = false
    }
}
```

如果在视图层次结构中找到多个滚动视图，则只有第一个滚动视图会调用您提供的闭包，并且会记录运行时问题。例如，在以下视图中，只有垂直滚动视图的阶段变化会调用提供的闭包。

```swift
VStack {
    ScrollView(.vertical) { ... }
    ScrollView(.horizontal) { ... }
}
.onScrollPhaseChange { ... }
```

## 响应滚动视图的变化

- **onScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行。

- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个操作，用于调用有关哪些视图被视为可见的信息。

- **onScrollVisibilityChange(threshold:_:)**：添加一个操作，当视图跨越阈值以被视为屏幕显示/隐藏时调用。

- **ScrollGeometry**：定义滚动视图几何体的类型。

- **ScrollPhase**：描述可滚动视图（例如滚动视图）的滚动手势状态的类型。

- **ScrollPhaseChangeContext**：当滚动视图的阶段发生变化时，提供更多内容的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onScrollPhaseChange(_:)
crawled: 2025-11-30T21:25:36Z
---

# onScrollPhaseChange(_:)

**Instance Method**

Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.

## Declaration

```swift
nonisolated func onScrollPhaseChange(_ action: @escaping (ScrollPhase, ScrollPhase) -> Void) -> some View

```

## Parameters

- **action**: A closure to run when the scroll phase changes.

## Discussion

Use this modifier to be informed of changes to a scroll view’s phase. A scroll view may be in a variety of different phases like panning or decelerating. See [ScrollPhase](../ScrollPhase.zh-Hans.md) for more information on the phases of a scroll view.

When the phase of a scroll view changes, the system invokes the action you provide. In the following example, a selection binding is updated when the scroll view transitions to the [decelerating](../ScrollPhase/decelerating.zh-Hans.md) or [idle](../ScrollPhase/idle.zh-Hans.md) phase.

```swift
@Binding var selection: SelectionValue?

ScrollView {
    // ...
}
.onScrollPhaseChange { _, newPhase in
    if newPhase == .decelerating || newPhase == .idle {
        selection = updateSelection()
    }
}
```

The system can also provide you with the geometry of the scroll view at the time of the phase change. You can use the geometry to understand where the scroll view has come or gone between the phase changes and update dependent state on that information. In the following example, whether toolbar content is hidden is determined based on the direction of the last user initiated scroll.

```swift
@Binding var hidesToolbarContent: Bool
@State private var lastOffset: CGFloat = 0.0

ScrollView {
    // ...
}
.onScrollPhaseChange { oldPhase, newPhase, context in
    if newPhase == .interacting {
        lastOffset = context.geometry.contentOffset.y
    }
    if oldPhase == .interacting, newPhase != .animating,
        context.geometry.contentOffset.y - lastOffset < 0.0
    {
        hidesToolbarContent = true
    } else {
        hidesToolbarContent = false
    }
}
```

If multiple scroll views are found within the view hierarchy, only the first one will invoke the closure you provide and a runtime issue will be logged. For example, in the following view, only the vertical scroll view will have its phase changes invoke the provided closure.

```swift
VStack {
    ScrollView(.vertical) { ... }
    ScrollView(.horizontal) { ... }
}
.onScrollPhaseChange { ... }
```

## Responding to scroll view changes

- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **ScrollGeometry**: A type that defines the geometry of a scroll view.
- **ScrollPhase**: A type that describes the state of a scroll gesture of a scrollable view like a scroll view.
- **ScrollPhaseChangeContext**: A type that provides you with more content when the phase of a scroll view changes.

