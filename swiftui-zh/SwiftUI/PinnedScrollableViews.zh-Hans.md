---
来源： https://developer.apple.com/documentation/SwiftUI/PinnedScrollableViews
抓取时间： 2025-12-02T17:38:07Z
---

# PinnedScrollableViews

**Structure**

可固定到滚动视图边界的视图类型集。

## 声明

```swift
struct PinnedScrollableViews
```

## 获取可滚动视图类型

- **sectionHeaders**：每个`Section` 的页眉视图将被固定。
- **sectionFooters**：每个`Section` 的页脚视图将被固定。

## 在一个维度中动态排列视图

- 使用懒堆栈视图对数据进行分组**：在懒堆栈视图中将内容分割成逻辑部分。
- 创建性能良好的可滚动堆栈**：使用滚动视图、堆栈视图和懒堆栈高效显示大量重复视图。
- **LazyHStack**：一种视图，可将其子视图排列成一条水平增长的线，只在需要时创建项目。
- **LazyVStack**：将其子视图排列成纵向增长的行的视图，只在需要时创建项目。

## 符合

- 等价
- 可表达数组字素
- 选项集
- 原始可表示
- 可发送
- 可发送元类
- 代数集


---
source: https://developer.apple.com/documentation/SwiftUI/PinnedScrollableViews
crawled: 2025-12-02T17:38:07Z
---

# PinnedScrollableViews

**Structure**

A set of view types that may be pinned to the bounds of a scroll view.

## Declaration

```swift
struct PinnedScrollableViews
```

## Getting scrollable view types

- **sectionHeaders**: The header view of each `Section` will be pinned.
- **sectionFooters**: The footer view of each `Section` will be pinned.

## Dynamically arranging views in one dimension

- **Grouping data with lazy stack views**: Split content into logical sections inside lazy stack views.
- **Creating performant scrollable stacks**: Display large numbers of repeated views efficiently with scroll views, stack views, and lazy stacks.
- **LazyHStack**: A view that arranges its children in a line that grows horizontally, creating items only as needed.
- **LazyVStack**: A view that arranges its children in a line that grows vertically, creating items only as needed.

## Conforms To

- Equatable
- ExpressibleByArrayLiteral
- OptionSet
- RawRepresentable
- Sendable
- SendableMetatype
- SetAlgebra

