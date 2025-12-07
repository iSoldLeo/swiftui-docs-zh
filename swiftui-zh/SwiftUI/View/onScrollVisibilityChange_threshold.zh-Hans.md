--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onScrollVisibilityChange(threshold:_:)

抓取时间：2025-12-02T17:40:31Z

---

# onScrollVisibilityChange(threshold:_:)

**实例方法**

添加一个操作，当视图跨越阈值以判断其是否在屏幕上显示/隐藏时，该操作将被调用。

## 声明

```swift
nonisolated func onScrollVisibilityChange(threshold: Double = 0.5, _ action: @escaping (Bool) -> Void) -> some View

```

## 参数

- **threshold**：视图在父视图视口中可见所需的比例，超过此比例后，将触发 `action` 操作。默认情况下，当视图在屏幕上的显示比例超过 50% 时，将调用此操作。

- **action**：达到阈值时将调用的操作。

## 讨论

使用此修饰符可在视图越过设定的阈值（即是否显示在屏幕上）时收到通知。

```swift
struct VideoPlayer: View {
    @State var playing: Bool

    var body: some View {
        Group {
            // ...
        }
        .onScrollVisibilityChange(threshold: 0.2) { isVisible in
            playing = isVisible
        }
    }
}
```

当视图出现在屏幕上时，如果已达到阈值，则会调用此操作。

## 响应滚动视图的变化

- **onScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行。

- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个操作，用于调用有关哪些视图将被视为可见的信息。

- **onScrollPhaseChange(_:)**：添加一个操作，当层次结构中第一个滚动视图的滚动阶段发生变化时执行。

- **ScrollGeometry**：定义滚动视图几何体的类型。

- **ScrollPhase**：描述可滚动视图（例如滚动视图）滚动手势状态的类型。

- **ScrollPhaseChangeContext**：当滚动视图的滚动阶段发生变化时，提供更多内容的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onScrollVisibilityChange(threshold:_:)
crawled: 2025-12-02T17:40:31Z
---

# onScrollVisibilityChange(threshold:_:)

**Instance Method**

Adds an action to be called when the view crosses the threshold to be considered on/off screen.

## Declaration

```swift
nonisolated func onScrollVisibilityChange(threshold: Double = 0.5, _ action: @escaping (Bool) -> Void) -> some View

```

## Parameters

- **threshold**: The amount required to be visible within the viewport of the parent view before the `action` is fired. By default when the view has crossed more than 50% on-screen, the action will be called.
- **action**: The action which will be called when the threshold has been reached.

## Discussion

Use this modifier to be informed when the view has crossed the provided threshold to be considered on/off screen.

```swift
struct VideoPlayer: View {
    @State var playing: Bool

    var body: some View {
        Group {
            // ...
        }
        .onScrollVisibilityChange(threshold: 0.2) { isVisible in
            playing = isVisible
        }
    }
}
```

When the view appears on-screen, the action will be called if the threshold has already been reached.

## Responding to scroll view changes

- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.
- **ScrollGeometry**: A type that defines the geometry of a scroll view.
- **ScrollPhase**: A type that describes the state of a scroll gesture of a scrollable view like a scroll view.
- **ScrollPhaseChangeContext**: A type that provides you with more content when the phase of a scroll view changes.

