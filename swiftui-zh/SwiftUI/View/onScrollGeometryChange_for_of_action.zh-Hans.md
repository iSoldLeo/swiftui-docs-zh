--- 来源：https://developer.apple.com/documentation/SwiftUI/View/onScrollGeometryChange(for:of:action:)

抓取时间：2025-12-02T17:40:30Z

---

# onScrollGeometryChange(for:of:action:)

**实例方法**

添加一个操作，当由滚动几何体创建的值发生变化时执行。

## 声明

```swift
nonisolated func onScrollGeometryChange<T>(for type: T.Type, of transform: @escaping (ScrollGeometry) -> T, action: @escaping (T, T) -> Void) -> some View where T : Equatable

```

## 参数

- **type**：由 [ScrollGeometry](../ScrollGeometry.zh-Hans.md) 转换而来的值的类型。

- **transform**：将 [ScrollGeometry](../ScrollGeometry.zh-Hans.md) 转换为您指定类型的闭包。

- **action**：当转换后的数据发生变化时要运行的闭包。

## 讨论

滚动视图的几何形状在滚动过程中会频繁变化。您应该避免在滚动几何形状发生变化时更新应用程序的大部分内容。为了帮助您做到这一点，您可以为此修饰符提供两个闭包：

- transform：此闭包将 [ScrollGeometry](../ScrollGeometry.zh-Hans.md) 的值转换为您自定义的数据类型。

- action：此闭包提供您在 `of` 中创建的数据类型，并在数据类型发生变化时调用。

例如，您可以使用此修饰符来检测用户何时将滚动视图滚动到其内容的顶部之外。在以下示例中，您转换为的数据类型是 `Bool`，并且当 `Bool` 发生变化时，将调用 action。

```swift
@Binding var isBeyondZero: Bool

ScrollView {
    // ...
}
.onScrollGeometryChange(for: Bool.self) { geometry in
    geometry.contentOffset.y < geometry.contentInsets.top
} action: { wasBeyondZero, isBeyondZero in
    self.isBeyondZero = isBeyondZero
}
```

如果在视图层次结构中找到多个滚动视图，则只有第一个滚动视图会调用您提供的闭包，并且会记录一个运行时问题。例如，在以下视图中，只有垂直滚动视图的几何体变化才会触发提供的闭包。

```swift
VStack {
    ScrollView(.vertical) { ... }
    ScrollView(.horizontal) { ... }
}
.onScrollGeometryChange(for: Bool.self) { geometry in
     ...
} action: { oldValue, newValue in
    ...
}
```

要响应非滚动视图的几何体变化，请参阅 [onGeometryChange(for:of:action:)](onGeometryChange_for_of_action.zh-Hans.md) 修饰符。

## 响应滚动视图的变化

- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个操作，用于调用有关哪些视图被视为可见的信息。

- **onScrollVisibilityChange(threshold:_:)**：添加一个操作，用于在视图跨越屏幕显示/隐藏阈值时调用。

- **onScrollPhaseChange(_:)**：添加一个操作，用于在层次结构中第一个滚动视图的滚动阶段发生变化时执行。

- **ScrollGeometry**：定义滚动视图几何体的类型。

- **ScrollPhase**：描述可滚动视图（例如滚动视图）滚动手势状态的类型。

- **ScrollPhaseChangeContext**：当滚动视图的滚动阶段发生变化时，提供更多内容的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/onScrollGeometryChange(for:of:action:)
crawled: 2025-12-02T17:40:30Z
---

# onScrollGeometryChange(for:of:action:)

**Instance Method**

Adds an action to be performed when a value, created from a scroll geometry, changes.

## Declaration

```swift
nonisolated func onScrollGeometryChange<T>(for type: T.Type, of transform: @escaping (ScrollGeometry) -> T, action: @escaping (T, T) -> Void) -> some View where T : Equatable

```

## Parameters

- **type**: The type of value transformed from a [ScrollGeometry](../ScrollGeometry.zh-Hans.md).
- **transform**: A closure that transforms a [ScrollGeometry](../ScrollGeometry.zh-Hans.md) to your type.
- **action**: A closure to run when the transformed data changes.

## Discussion

The geometry of a scroll view changes frequently while scrolling. You should avoid updating large parts of your app whenever the scroll geometry changes. To aid in this, you provide two closures to this modifier:

- transform: This converts a value of [ScrollGeometry](../ScrollGeometry.zh-Hans.md) to a your own data type.
- action: This provides the data type you created in `of` and is called whenever the data type changes.

For example, you can use this modifier to know when the user scrolls a scroll view beyond the top of its content. In the following example, the data type you convert to is a `Bool` and the action is called whenever the `Bool` changes.

```swift
@Binding var isBeyondZero: Bool

ScrollView {
    // ...
}
.onScrollGeometryChange(for: Bool.self) { geometry in
    geometry.contentOffset.y < geometry.contentInsets.top
} action: { wasBeyondZero, isBeyondZero in
    self.isBeyondZero = isBeyondZero
}
```

If multiple scroll views are found within the view hierarchy, only the first one will invoke the closure you provide and a runtime issue will be logged. For example, in the following view, only the vertical scroll view will have its geometry changes invoke the provided closure.

```swift
VStack {
    ScrollView(.vertical) { ... }
    ScrollView(.horizontal) { ... }
}
.onScrollGeometryChange(for: Bool.self) { geometry in
     ...
} action: { oldValue, newValue in
    ...
}
```

For responding to non-scroll geometry changes, see the [onGeometryChange(for:of:action:)](onGeometryChange_for_of_action.zh-Hans.md) modifier.

## Responding to scroll view changes

- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.
- **ScrollGeometry**: A type that defines the geometry of a scroll view.
- **ScrollPhase**: A type that describes the state of a scroll gesture of a scrollable view like a scroll view.
- **ScrollPhaseChangeContext**: A type that provides you with more content when the phase of a scroll view changes.

