--- 来源：https://developer.apple.com/documentation/SwiftUI/ScrollTarget
抓取时间：2025-12-02T17:40:20Z

---

# ScrollTarget

**Structure**

定义滚动视图尝试滚动的目标位置的类型。

## 声明

```swift
struct ScrollTarget
```

## 获取滚动目标

- **anchor**：滚动视图可见区域内矩形的对齐锚点。

- **rect**：滚动视图尝试滚动到的矩形区域。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可滚动视图在指定轴上的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTargetBehavior**：定义可滚动视图滚动行为的类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **PagingScrollTargetBehavior**：将滚动目标与基于容器的几何体对齐的滚动行为。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与基于视图的几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：已擦除类型的滚动目标行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。

## 符合以下标准

- 可复制

- 可等价比较

- 可哈希


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollTarget
crawled: 2025-12-02T17:40:20Z
---

# ScrollTarget

**Structure**

A type defining the target in which a scroll view should try and scroll to.

## Declaration

```swift
struct ScrollTarget
```

## Getting the scroll target

- **anchor**: The anchor to which the rect should be aligned within the visible region of the scrollable view.
- **rect**: The rect that a scrollable view should try and have contained.

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **ScrollTargetBehaviorContext**: The context in which a scroll target behavior updates its scroll target.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

## Conforms To

- Copyable
- Equatable
- Hashable

