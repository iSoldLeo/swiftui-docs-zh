--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollTargetLayout(isEnabled:)

抓取时间：2025-11-30T21:25:23Z

---

# scrollTargetLayout(isEnabled:)

**实例方法**

将最外层布局配置为滚动目标布局。

## 声明

```swift
nonisolated func scrollTargetLayout(isEnabled: Bool = true) -> some View

```

## 说明

此修饰符与 [ViewAlignedScrollTargetBehavior](../ViewAlignedScrollTargetBehavior.zh-Hans.md) 配合使用，以确保滚动视图与基于视图的内容对齐。

将此修饰符应用于布局容器，例如 [LazyHStack](../LazyHStack.zh-Hans.md) 或 [VStack](../VStack.zh-Hans.md)，这些容器位于 [ScrollView](../ScrollView.zh-Hans.md) 内，用于容纳 [ScrollView](../ScrollView.zh-Hans.md) 的主要重复内容。

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 10.0) {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollTargetBehavior(.viewAligned)
```

滚动目标布局便于将 `View/scrollTarget(isEnabled:)` 修饰符应用于布局中的每个视图。

滚动目标布局可确保嵌套在主布局内的任何目标布局都不会也成为滚动目标布局。

```swift
LazyHStack { // a scroll target layout
    VStack { ... } // not a scroll target layout
    LazyHStack { ... } // also not a scroll target layout
}
.scrollTargetLayout()
```

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可滚动视图在指定轴上的滚动行为。

- **ScrollTarget**：定义滚动视图尝试滚动到的目标类型。

- **ScrollTargetBehavior**：定义可滚动视图的滚动行为类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **PagingScrollTargetBehavior**：将滚动目标与容器几何体对齐的滚动行为。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与视图几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：类型擦除后的滚动目标行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollTargetLayout(isEnabled:)
crawled: 2025-11-30T21:25:23Z
---

# scrollTargetLayout(isEnabled:)

**Instance Method**

Configures the outermost layout as a scroll target layout.

## Declaration

```swift
nonisolated func scrollTargetLayout(isEnabled: Bool = true) -> some View

```

## Discussion

This modifier works together with the [ViewAlignedScrollTargetBehavior](../ViewAlignedScrollTargetBehavior.zh-Hans.md) to ensure that scroll views align to view based content.

Apply this modifier to layout containers like [LazyHStack](../LazyHStack.zh-Hans.md) or [VStack](../VStack.zh-Hans.md) within a [ScrollView](../ScrollView.zh-Hans.md) that contain the main repeating content of your [ScrollView](../ScrollView.zh-Hans.md).

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 10.0) {
        ForEach(items) { item in
            ItemView(item)
        }
    }
    .scrollTargetLayout()
}
.scrollTargetBehavior(.viewAligned)
```

Scroll target layouts act as a convenience for applying a `View/scrollTarget(isEnabled:)` modifier to each views in the layout.

A scroll target layout will ensure that any target layout nested within the primary one will not also become a scroll target layout.

```swift
LazyHStack { // a scroll target layout
    VStack { ... } // not a scroll target layout
    LazyHStack { ... } // also not a scroll target layout
}
.scrollTargetLayout()
```

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

