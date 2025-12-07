--- 来源：https://developer.apple.com/documentation/SwiftUI/ViewAlignedScrollTargetBehavior
抓取时间：2025-12-02T17:40:23Z

---

# ViewAlignedScrollTargetBehavior

**Structure**

将滚动目标与基于视图的几何体对齐的滚动行为。

## 声明

```swift
struct ViewAlignedScrollTargetBehavior
```

## 概述

当滚动视图应始终将其滚动目标与一个与视图几何体对齐的矩形对齐时，可以使用此行为。在以下示例中，滚动视图始终选择一个项目视图作为最终目标。

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
.padding(.horizontal, 20.0)
```

您可以使用 [scrollTargetLayout(isEnabled:)](View/scrollTargetLayout_isEnabled.zh-Hans.md) 修饰符配置用于最终目标的视图。将此修饰符应用于布局容器（例如 [LazyVStack](LazyVStack.zh-Hans.md) 或 [HStack](HStack.zh-Hans.md)），布局中的每个视图都将被考虑进行对齐。

您可以使用 [LimitBehavior](ViewAlignedScrollTargetBehavior/LimitBehavior.zh-Hans.md) 类型自定义视图对齐行为是否限制一次可滚动的视图数量。提供值 [always](ViewAlignedScrollTargetBehavior/LimitBehavior/always.zh-Hans.md) 可使该行为始终只允许一次滚动少量视图。

默认情况下，当视图处于紧凑的水平尺寸类别且可沿水平轴滚动时，视图对齐行为会限制其滚动的视图数量；当视图处于紧凑的垂直尺寸类别且可沿垂直轴滚动时，视图对齐行为也会限制其滚动的视图数量；否则，不会限制可滚动的视图数量。

## 创建目标行为

- **init(limitBehavior:)**：创建视图对齐滚动行为。

- **ViewAlignedScrollTargetBehavior.LimitBehavior**：定义一次可滚动视图数量的类型。

## 初始化器

- **init(anchor:)**：使用提供的锚点创建视图对齐滚动行为。

- **init(limitBehavior:anchor:)**：使用提供的限制行为和锚点创建视图对齐滚动行为。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可滚动视图在指定轴上的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTarget**：定义滚动视图应尝试滚动到的目标位置的类型。

- **ScrollTargetBehavior**：定义可滚动视图的滚动行为的类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **PagingScrollTargetBehavior**：将滚动目标与容器几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：类型擦除的滚动目标行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。

## 符合以下规范

- ScrollTargetBehavior


---
source: https://developer.apple.com/documentation/SwiftUI/ViewAlignedScrollTargetBehavior
crawled: 2025-12-02T17:40:23Z
---

# ViewAlignedScrollTargetBehavior

**Structure**

The scroll behavior that aligns scroll targets to view-based geometry.

## Declaration

```swift
struct ViewAlignedScrollTargetBehavior
```

## Overview

You use this behavior when a scroll view should always align its scroll targets to a rectangle that’s aligned to the geometry of a view. In the following example, the scroll view always picks an item view to settle on.

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
.padding(.horizontal, 20.0)
```

You configure which views should be used for settling using the [scrollTargetLayout(isEnabled:)](View/scrollTargetLayout_isEnabled.zh-Hans.md) modifier. Apply this modifier to a layout container like [LazyVStack](LazyVStack.zh-Hans.md) or [HStack](HStack.zh-Hans.md) and each individual view in that layout will be considered for alignment.

You can customize whether the view aligned behavior limits the number of views that can be scrolled at a time by using the [LimitBehavior](ViewAlignedScrollTargetBehavior/LimitBehavior.zh-Hans.md) type. Provide a value of [always](ViewAlignedScrollTargetBehavior/LimitBehavior/always.zh-Hans.md) to always have the behavior only allow a few views to be scrolled at a time.

By default, the view aligned behavior will limit the number of views it scrolls when in a compact horizontal size class when scrollable in the horizontal axis, when in a compact vertical size class when scrollable in the vertical axis, and otherwise does not impose any limit on the number of views that can be scrolled.

## Creating the target behavior

- **init(limitBehavior:)**: Creates a view aligned scroll behavior.
- **ViewAlignedScrollTargetBehavior.LimitBehavior**: A type that defines the amount of views that can be scrolled at a time.

## Initializers

- **init(anchor:)**: Creates a view aligned scroll behavior with the provided anchor.
- **init(limitBehavior:anchor:)**: Creates a view aligned scroll behavior with the provided limit behavior and anchor.

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

## Conforms To

- ScrollTargetBehavior

