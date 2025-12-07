---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehaviorPropertiesContext
抓取时间： 2025-12-02T17:40:26Z
---

# ScrollTargetBehaviorPropertiesContext

**Structure**

滚动目标行为决定其属性的上下文。

## 声明

```swift
struct ScrollTargetBehaviorPropertiesContext
```

## 实例属性

- **axes**：滚动视图的可滚动轴。
- **environment**：滚动视图的环境。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可在提供的轴上滚动的视图的滚动行为。
- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。
- **ScrollTarget**：定义滚动视图应尝试滚动到的目标的类型。
- **ScrollTargetBehavior**：定义可滚动视图的滚动行为的类型。
- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。
- **PagingScrollTargetBehavior**：将滚动目标对齐到基于容器的几何体的滚动行为。
- **ViewAlignedScrollTargetBehavior**：使滚动目标与基于视图的几何体对齐的滚动行为。
- **AnyScrollTargetBehavior**：一种按类型对齐的滚动目标行为。
- **ScrollTargetBehaviorProperties**：影响滚动目标行为适用的滚动视图的属性。


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehaviorPropertiesContext
crawled: 2025-12-02T17:40:26Z
---

# ScrollTargetBehaviorPropertiesContext

**Structure**

The context in which a scroll target behavior can decide its properties.

## Declaration

```swift
struct ScrollTargetBehaviorPropertiesContext
```

## Instance Properties

- **axes**: The scrollable axes of the scroll view.
- **environment**: The environment of the scroll view.

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.

