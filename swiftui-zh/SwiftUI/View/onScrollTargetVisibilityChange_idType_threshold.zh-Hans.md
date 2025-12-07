--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onScrollTargetVisibilityChange(idType:threshold:_:)

抓取时间：2025-12-02T17:40:31Z

---

# onScrollTargetVisibilityChange(idType:threshold:_:)

**实例方法**

添加一个操作，用于传递有关哪些视图被视为可见的信息。

## 声明

```swift
nonisolated func onScrollTargetVisibilityChange<ID>(idType: ID.Type, threshold: Double = 0.5, _ action: @escaping ([ID]) -> Void) -> some View where ID : Hashable

```

## 参数

- **idType**：子视图提供的标识类型。

- **threshold**：触发 `action` 之前，滚动视图视口内需要显示的视图数量。默认情况下，当视图在屏幕上的显示比例超过 50% 时，将调用此操作。

- **action**：当滚动视图中的视图超过指定的阈值时，将调用此操作。回调函数将包含哪些视图被视为可见的信息。

## 讨论

将此修饰符与修饰符 `View/scrollTargetLayout()` 一起使用，以便在目标滚动视图中的视图超过指定的阈值（即被视为在屏幕上显示/隐藏）时收到通知。

```swift
ScrollView {
    LazyVStack {
        ForEach(models) { model in
            CardView(model: model)
        }
    }
    .scrollTargetLayout()
}
.onScrollTargetVisibilityChange(for: Model.ID.self, threshold: 0.2) { onScreenCards in
    // Disable video playback for cards that are offscreen...
}
```

## 响应滚动视图的变化

- **onScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行。

- **onScrollVisibilityChange(threshold:_:)**：添加一个操作，当视图超过阈值（即被视为在屏幕上显示/隐藏）时调用。

- **onScrollPhaseChange(_:)**：添加一个操作，当层级结构中第一个滚动视图的滚动阶段发生变化时执行。

- **ScrollGeometry**：定义滚动视图几何形状的类型。

- **ScrollPhase**：描述可滚动视图（例如滚动视图）滚动手势状态的类型。

- **ScrollPhaseChangeContext**：当滚动视图的滚动阶段发生变化时，提供更多内容的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onScrollTargetVisibilityChange(idType:threshold:_:)
crawled: 2025-12-02T17:40:31Z
---

# onScrollTargetVisibilityChange(idType:threshold:_:)

**Instance Method**

Adds an action to be called with information about what views would be considered visible.

## Declaration

```swift
nonisolated func onScrollTargetVisibilityChange<ID>(idType: ID.Type, threshold: Double = 0.5, _ action: @escaping ([ID]) -> Void) -> some View where ID : Hashable

```

## Parameters

- **idType**: The type of Identity provided by the subviews.
- **threshold**: The amount required to be visible within the viewport of the the scrollview before the `action` is fired.  By default when the view has crossed more than 50% on-screen, the action will be called.
- **action**: The action which will be called when the views within the scroll view cross the provided threshold. The callback will include which views are considered visible.

## Discussion

Use this modifier along with the modifier `View/scrollTargetLayout()` to be informed when the views in the targetted scroll view have crossed the provided threshold to be considered on/off screen.

```swift
ScrollView {
    LazyVStack {
        ForEach(models) { model in
            CardView(model: model)
        }
    }
    .scrollTargetLayout()
}
.onScrollTargetVisibilityChange(for: Model.ID.self, threshold: 0.2) { onScreenCards in
    // Disable video playback for cards that are offscreen...
}
```

## Responding to scroll view changes

- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.
- **ScrollGeometry**: A type that defines the geometry of a scroll view.
- **ScrollPhase**: A type that describes the state of a scroll gesture of a scrollable view like a scroll view.
- **ScrollPhaseChangeContext**: A type that provides you with more content when the phase of a scroll view changes.

