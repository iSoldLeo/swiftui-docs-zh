--- 来源：https://developer.apple.com/documentation/SwiftUI/PagingScrollTargetBehavior
抓取时间：2025-12-02T17:40:23Z

---

# 分页滚动目标行为

**Structure**

将滚动目标与容器的几何形状对齐的滚动行为。

## 声明

```swift
struct PagingScrollTargetBehavior
```

## 概述

在以下示例中，惰性堆栈中的每个视图都可以双向灵活滚动，滚动视图会固定在与容器对齐的边界上。

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

## 创建目标行为

- **init()**：创建分页滚动行为。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可沿指定轴滚动的视图的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTarget**：定义滚动视图尝试滚动到的目标类型。

- **ScrollTargetBehavior**：定义可滚动视图的滚动行为类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与基于视图的几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：类型擦除后的滚动目标行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。

## 符合以下规范

- ChartScrollTargetBehavior

- Copyable

- ScrollTargetBehavior


---
source: https://developer.apple.com/documentation/SwiftUI/PagingScrollTargetBehavior
crawled: 2025-12-02T17:40:23Z
---

# PagingScrollTargetBehavior

**Structure**

The scroll behavior that aligns scroll targets to container-based geometry.

## Declaration

```swift
struct PagingScrollTargetBehavior
```

## Overview

In the following example, every view in the lazy stack is flexible in both directions and the scroll view settles to container-aligned boundaries.

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

## Creating the target behavior

- **init()**: Creates a paging scroll behavior.

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

## Conforms To

- ChartScrollTargetBehavior
- Copyable
- ScrollTargetBehavior

