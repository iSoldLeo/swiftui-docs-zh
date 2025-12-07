--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehaviorProperties
抓取时间：2025-12-02T17:40:25Z

---

# ScrollTargetBehaviorProperties

**Structure**

影响滚动目标行为所应用的滚动视图的属性。

## 声明

```swift
struct ScrollTargetBehaviorProperties
```

## 初始化器

- **init()**：创建一组默认属性。

## 实例属性

- **limitsScrolls**：此滚动目标行为是否应限制滚动视图的默认滚动距离。启用后，滚动视图会优先滚动较短的距离。默认情况下，此功能未启用。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可沿指定轴滚动的视图的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTarget**：定义滚动视图尝试滚动到的目标类型。

- **ScrollTargetBehavior**：定义可滚动视图的滚动行为类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **PagingScrollTargetBehavior**：将滚动目标与基于容器的几何体对齐的滚动行为。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与基于视图的几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：类型擦除后的滚动目标行为。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为决定其属性的上下文。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTargetBehaviorProperties
crawled: 2025-12-02T17:40:25Z
---

# ScrollTargetBehaviorProperties

**Structure**

Properties influencing the scroll view a scroll target behavior applies to.

## Declaration

```swift
struct ScrollTargetBehaviorProperties
```

## Initializers

- **init()**: Creates a default set of properties.

## Instance Properties

- **limitsScrolls**: Whether this scroll target behavior should limit the distance a scroll view scrolls by default. When enabled, the scroll view prefers to scroll a shorter distance. By default, this is not enabled.

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

