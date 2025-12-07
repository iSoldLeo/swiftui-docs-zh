--- 来源：https://developer.apple.com/documentation/SwiftUI/AnyScrollTargetBehavior
抓取时间：2025-12-02T17:40:24Z

---

# AnyScrollTargetBehavior

**Structure**

类型擦除滚动目标行为。

## 声明

```swift
@frozen struct AnyScrollTargetBehavior
```

## 概述

将此属性提供给 [scrollTargetBehavior(_:)](View/scrollTargetBehavior.zh-Hans.md) 修饰符。当底层行为发生变化时，应用此行为的滚动视图将会更新。

使用此属性可在运行时动态控制滚动目标行为。例如，您可以在紧凑尺寸类中提供分页行为，而在其他情况下提供视图对齐行为。

```swift
@Environment(\.horizontalSizeClass) var sizeClass

var body: some View {
    ScrollView { ... }
        .scrollTargetBehavior(scrollTargetBehavior)
}

 var scrollTargetBehavior: some ScrollTargetBehavior {
    sizeClass == .compact
        ? AnyScrollTargetBehavior(.paging)
        : AnyScrollTargetBehavior(.viewAligned)
}
```

## 初始化器

- **init(_:)**：创建新的类型擦除滚动目标行为。

## 实例属性

- **base**：类型擦除后的滚动目标行为。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可沿指定轴滚动的视图的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTarget**：定义滚动视图应尝试滚动到的目标类型的类型。

- **ScrollTargetBehavior**：定义可滚动视图的滚动行为的类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **PagingScrollTargetBehavior**：将滚动目标与基于容器的几何体对齐的滚动行为。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与基于视图的几何体对齐的滚动行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。

## 符合以下规范

- ScrollTargetBehavior


---
source: https://developer.apple.com/documentation/SwiftUI/AnyScrollTargetBehavior
crawled: 2025-12-02T17:40:24Z
---

# AnyScrollTargetBehavior

**Structure**

A type-erased scroll target behavior.

## Declaration

```swift
@frozen struct AnyScrollTargetBehavior
```

## Overview

Provide this to the [scrollTargetBehavior(_:)](View/scrollTargetBehavior.zh-Hans.md) modifier. When the underlying behavior changes, the scroll view to which this behavior applies will be updated.

Use this to dynamically control the scroll target behavior at runtime. For example, you could provide a paging behavior in compact size classes and a view aligned behavior otherwise.

```swift
@Environment(\.horizontalSizeClass) var sizeClass

var body: some View {
    ScrollView { ... }
        .scrollTargetBehavior(scrollTargetBehavior)
}

 var scrollTargetBehavior: some ScrollTargetBehavior {
    sizeClass == .compact
        ? AnyScrollTargetBehavior(.paging)
        : AnyScrollTargetBehavior(.viewAligned)
}
```

## Initializers

- **init(_:)**: Creates a new type-erase scroll target behavior.

## Instance Properties

- **base**: The type-erased scroll target behavior.

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

## Conforms To

- ScrollTargetBehavior

