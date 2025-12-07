--- 来源：https://developer.apple.com/documentation/SwiftUI/View/scrollTargetBehavior(_:)

抓取时间：2025-12-02T17:40:19Z

---

# scrollTargetBehavior(_:)

**实例方法**

设置可滚动视图在指定轴上的滚动行为。

## 声明

```swift
nonisolated func scrollTargetBehavior(_ behavior: some ScrollTargetBehavior) -> some View

```

## 讨论

默认情况下，可滚动视图会根据其减速率和滚动手势的状态来计算滚动手势的结束位置。滚动行为允许您自定义此逻辑。您可以提供自己的滚动行为，[ScrollTargetBehavior](../ScrollTargetBehavior.zh-Hans.md)，也可以使用 SwiftUI 提供的内置滚动行为之一。

### 分页行为

SwiftUI 提供了一种名为 [PagingScrollTargetBehavior](../PagingScrollTargetBehavior.zh-Hans.md) 的行为，它利用滚动视图的几何形状来决定滚动的结束位置。

在以下示例中，惰性堆栈中的每个视图都可以双向滚动，滚动视图最终会停留在容器的边界上。

```swift
ScrollView {
    LazyVStack(spacing: 0.0) {
        ForEach(items) { item in
            FullScreenItem(item)
        }
    }
}
.scrollTargetBehavior(.paging)
```

### 视图对齐行为

SwiftUI 提供了一种名为 [ViewAlignedScrollTargetBehavior](../ViewAlignedScrollTargetBehavior.zh-Hans.md) 的滚动行为，它始终会停留在各个视图的几何形状上。

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
.safeAreaPadding(.horizontal, 20.0)
```

您可以使用 [scrollTargetLayout(isEnabled:)](scrollTargetLayout_isEnabled.zh-Hans.md) 修饰符来配置哪些视图应该用于对齐。将此修饰符应用于布局容器（例如 [LazyVStack](../LazyVStack.zh-Hans.md) 或 [HStack](../HStack.zh-Hans.md)），布局中的每个视图都将被考虑用于对齐。

## 定义滚动目标

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTarget**：定义滚动视图尝试滚动到的目标类型。

- **ScrollTargetBehavior**：定义可滚动视图的滚动行为类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **PagingScrollTargetBehavior**：将滚动目标与容器几何体对齐的滚动行为。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与视图几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：类型擦除后的滚动目标行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为决定其属性的上下文。


---
source: https://developer.apple.com/documentation/SwiftUI/View/scrollTargetBehavior(_:)
crawled: 2025-12-02T17:40:19Z
---

# scrollTargetBehavior(_:)

**Instance Method**

Sets the scroll behavior of views scrollable in the provided axes.

## Declaration

```swift
nonisolated func scrollTargetBehavior(_ behavior: some ScrollTargetBehavior) -> some View

```

## Discussion

A scrollable view calculates where scroll gestures should end using its deceleration rate and the state of its scroll gesture by default. A scroll behavior allows for customizing this logic. You can provide your own [ScrollTargetBehavior](../ScrollTargetBehavior.zh-Hans.md) or use one of the built in behaviors provided by SwiftUI.

### Paging Behavior

SwiftUI offers a [PagingScrollTargetBehavior](../PagingScrollTargetBehavior.zh-Hans.md) behavior which uses the geometry of the scroll view to decide where to allow scrolls to end.

In the following example, every view in the lazy stack is flexible in both directions and the scroll view will settle to container aligned boundaries.

```swift
ScrollView {
    LazyVStack(spacing: 0.0) {
        ForEach(items) { item in
            FullScreenItem(item)
        }
    }
}
.scrollTargetBehavior(.paging)
```

### View Aligned Behavior

SwiftUI offers a [ViewAlignedScrollTargetBehavior](../ViewAlignedScrollTargetBehavior.zh-Hans.md) scroll behavior that will always settle on the geometry of individual views.

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
.safeAreaPadding(.horizontal, 20.0)
```

You configure which views should be used for settling using the [scrollTargetLayout(isEnabled:)](scrollTargetLayout_isEnabled.zh-Hans.md) modifier. Apply this modifier to a layout container like [LazyVStack](../LazyVStack.zh-Hans.md) or [HStack](../HStack.zh-Hans.md) and each individual view in that layout will be considered for alignment.

## Defining scroll targets

- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

