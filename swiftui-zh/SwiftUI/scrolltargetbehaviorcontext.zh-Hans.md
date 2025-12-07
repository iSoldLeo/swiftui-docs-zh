--- 来源：https://developer.apple.com/documentation/swiftui/scrolltargetbehaviorcontext
抓取时间：2025-12-04T13:37:18Z

---

# ScrollTargetBehaviorContext

**Structure**

滚动目标行为更新其滚动目标时所处的上下文。

## 声明

```swift
@dynamicMemberLookup struct ScrollTargetBehaviorContext
```

## 获取滚动目标行为上下文

- **axes**：可滚动视图的滚动轴。

- **containerSize**：可滚动视图容器的大小。

- **contentSize**：可滚动视图内容的大小。

- **originalTarget**：滚动手势开始时的原始目标。

- **velocity**：可滚动视图当前滚动速度。

## 访问上下文

- **subscript(dynamicMember:)**

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可沿指定轴滚动的视图的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTarget**：定义滚动视图尝试滚动到的目标类型的类型。

- **ScrollTargetBehavior**：定义可滚动视图滚动行为的类型。

- **PagingScrollTargetBehavior**：将滚动目标与容器几何体对齐的滚动行为。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与基于视图的几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：类型擦除后的滚动目标行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。


---
source: https://developer.apple.com/documentation/swiftui/scrolltargetbehaviorcontext
crawled: 2025-12-04T13:37:18Z
---

# ScrollTargetBehaviorContext

**Structure**

The context in which a scroll target behavior updates its scroll target.

## Declaration

```swift
@dynamicMemberLookup struct ScrollTargetBehaviorContext
```

## Getting the scroll target behavior context

- **axes**: The axes in which the scrollable view is scrollable.
- **containerSize**: The size of the container of the scrollable view.
- **contentSize**: The size of the content of the scrollable view.
- **originalTarget**: The original target when the scroll gesture began.
- **velocity**: The current velocity of the scrollable view’s scroll gesture.

## Accessing the context

- **subscript(dynamicMember:)**

## Defining scroll targets

- **scrollTargetBehavior(_:)**: Sets the scroll behavior of views scrollable in the provided axes.
- **scrollTargetLayout(isEnabled:)**: Configures the outermost layout as a scroll target layout.
- **ScrollTarget**: A type defining the target in which a scroll view should try and scroll to.
- **ScrollTargetBehavior**: A type that defines the scroll behavior of a scrollable view.
- **PagingScrollTargetBehavior**: The scroll behavior that aligns scroll targets to container-based geometry.
- **ViewAlignedScrollTargetBehavior**: The scroll behavior that aligns scroll targets to view-based geometry.
- **AnyScrollTargetBehavior**: A type-erased scroll target behavior.
- **ScrollTargetBehaviorProperties**: Properties influencing the scroll view a scroll target behavior applies to.
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

