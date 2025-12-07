---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior
抓取时间： 2025-12-02T17:40:21Z
---

# 滚动目标行为

**Protocol**

定义可滚动视图的滚动行为的类型。

### 声明

```swift
protocol ScrollTargetBehavior
```

## 概览

默认情况下，可滚动视图会使用其减速率和滚动手势的状态来计算滚动手势的结束位置。滚动行为允许自定义这一逻辑。

您可以使用 [updateTarget(_:context:)](ScrollTargetBehavior/updateTarget___context.zh-Hans.md) 方法定义滚动行为。

使用该方法，您可以控制某人在可滚动视图中滚动的位置。例如，您可以通过以下操作创建一个每 10 点对齐的自定义滚动行为：

```swift
struct BasicScrollTargetBehavior: ScrollTargetBehavior {
    func updateTarget(_ target: inout Target, context: TargetContext) {
        // Align to every 1/10 the size of the scroll view.
        target.rect.x.round(
            toMultipleOf: round(context.containerSize.width / 10.0))
    }
}
```

### 分页行为

SwiftUI 提供内置的滚动行为。其中一种行为是 [PagingScrollTargetBehavior](PagingScrollTargetBehavior.zh-Hans.md)，它使用滚动视图的几何形状来决定允许滚动结束的位置。

在下面的示例中，懒人堆栈中的每个视图在两个方向上都是灵活的，滚动视图将固定在容器对齐的边界上。

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

SwiftUI 还提供了一种 [ViewAlignedScrollTargetBehavior](ViewAlignedScrollTargetBehavior.zh-Hans.md) 滚动行为，该行为始终会在各个视图的几何图形上对齐。

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

您可以使用[scrollTargetLayout(isEnabled:)](View/scrollTargetLayout_isEnabled.zh-Hans.md)修改器配置哪些视图应用于结算。将该修饰符应用于 [LazyVStack](LazyVStack.zh-Hans.md) 或 [HStack](HStack.zh-Hans.md) 等布局容器，该布局中的每个视图都将被考虑进行对齐。

使用带[scrollTargetBehavior(_:)](View/scrollTargetBehavior.zh-Hans.md)修饰符的符合本协议的类型。

## 获取滚动目标行为

- **paging**：将滚动目标与基于容器的几何体对齐的滚动行为。
- **viewAligned**：使滚动目标与基于视图的几何体对齐的滚动行为。
- **viewAligned(limitBehavior:)**：使滚动目标与基于视图的几何体对齐的滚动行为。

## 更新建议目标

- **updateTarget(_:context:)**：更新可滚动视图应滚动到的建议目标。
- **ScrollTargetBehavior.TargetContext**：滚动行为更新滚动目标的上下文。

### 实例方法

- **properties(context:)**：此行为的属性

## 类型别名

- **ScrollTargetBehavior.Properties**：滚动行为的属性
- **ScrollTargetBehavior.PropertiesContext**：滚动行为的属性上下文。

### 类型方法

- **viewAligned(anchor:)**：滚动行为的属性上下文：将滚动目标与基于视图的几何体对齐的滚动行为。
- **viewAligned(limitBehavior:anchor:)**：使滚动目标与基于视图的几何体对齐的滚动行为。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可在所提供的轴上滚动的视图的滚动行为。
- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。
- **ScrollTarget**：定义滚动视图应尝试滚动到的目标的类型。
- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。
- **PagingScrollTargetBehavior**：将滚动目标对齐到基于容器的几何体的滚动行为。
- **ViewAlignedScrollTargetBehavior**：使滚动目标与基于视图的几何体对齐的滚动行为。
- **AnyScrollTargetBehavior**：一种按类型对齐的滚动目标行为。
- **ScrollTargetBehaviorProperties**：影响滚动目标行为适用的滚动视图的属性。
- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。

## 符合类型

- 任意滚动目标行为
- 分页滚动目标行为
- ViewAlignedScrollTargetBehavior


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehavior
crawled: 2025-12-02T17:40:21Z
---

# ScrollTargetBehavior

**Protocol**

A type that defines the scroll behavior of a scrollable view.

## Declaration

```swift
protocol ScrollTargetBehavior
```

## Overview

A scrollable view calculates where scroll gestures should end using its deceleration rate and the state of its scroll gesture by default. A scroll behavior allows for customizing this logic.

You define a scroll behavior using the [updateTarget(_:context:)](ScrollTargetBehavior/updateTarget___context.zh-Hans.md) method.

Using this method, you can control where someone can scroll in a scrollable view. For example, you can create a custom scroll behavior that aligns to every 10 points by doing the following:

```swift
struct BasicScrollTargetBehavior: ScrollTargetBehavior {
    func updateTarget(_ target: inout Target, context: TargetContext) {
        // Align to every 1/10 the size of the scroll view.
        target.rect.x.round(
            toMultipleOf: round(context.containerSize.width / 10.0))
    }
}
```

### Paging Behavior

SwiftUI offers built in scroll behaviors. One such behavior is the [PagingScrollTargetBehavior](PagingScrollTargetBehavior.zh-Hans.md) which uses the geometry of the scroll view to decide where to allow scrolls to end.

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

SwiftUI also offers a [ViewAlignedScrollTargetBehavior](ViewAlignedScrollTargetBehavior.zh-Hans.md) scroll behavior that will always settle on the geometry of individual views.

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

You configure which views should be used for settling using the [scrollTargetLayout(isEnabled:)](View/scrollTargetLayout_isEnabled.zh-Hans.md) modifier. Apply this modifier to a layout container like [LazyVStack](LazyVStack.zh-Hans.md) or [HStack](HStack.zh-Hans.md) and each individual view in that layout will be considered for alignment.

Use types conforming to this protocol with the [scrollTargetBehavior(_:)](View/scrollTargetBehavior.zh-Hans.md) modifier.

## Getting the scroll target behavior

- **paging**: The scroll behavior that aligns scroll targets to container-based geometry.
- **viewAligned**: The scroll behavior that aligns scroll targets to view-based geometry.
- **viewAligned(limitBehavior:)**: The scroll behavior that aligns scroll targets to view-based geometry.

## Updating the proposed target

- **updateTarget(_:context:)**: Updates the proposed target that a scrollable view should scroll to.
- **ScrollTargetBehavior.TargetContext**: The context in which a scroll behavior updates the scroll target.

## Instance Methods

- **properties(context:)**: Properties of this behavior

## Type Aliases

- **ScrollTargetBehavior.Properties**: The properties of a scroll behavior
- **ScrollTargetBehavior.PropertiesContext**: The properties context of a scroll behavior.

## Type Methods

- **viewAligned(anchor:)**: The scroll behavior that aligns scroll targets to view-based geometry.
- **viewAligned(limitBehavior:anchor:)**: The scroll behavior that aligns scroll targets to view-based geometry.

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

## Conforming Types

- AnyScrollTargetBehavior
- PagingScrollTargetBehavior
- ViewAlignedScrollTargetBehavior

