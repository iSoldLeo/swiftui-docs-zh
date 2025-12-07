---
来源： https://developer.apple.com/documentation/SwiftUI/ScrollAnchorRole
抓取时间： 2025-12-02T17:40:17Z
---

# ScrollAnchorRole

**Structure**

定义滚动锚点角色的类型。

### 声明

```swift
struct ScrollAnchorRole
```

## 概览

您可以使用[defaultScrollAnchor(_:)](View/defaultScrollAnchor.zh-Hans.md)修饰符将[UnitPoint](UnitPoint.zh-Hans.md) 与[ScrollView](ScrollView.zh-Hans.md) 关联起来。默认情况下，系统将此点用于不同类型的行为，包括

- 滚动视图最初应在何处滚动
- 滚动视图应如何处理内容大小或容器大小的变化
- 滚动视图应如何对齐小于其容器尺寸的内容

你可以为这些不同的角色分配不同的单元点，从而进一步自定义这种行为。

### 类型属性

- **alignment**：当滚动视图的内容尺寸小于滚动视图的容器尺寸时，影响滚动视图如何对齐其内容的角色。
- **initialOffset**：影响滚动视图初始滚动位置的作用。
- **sizeChanges**：当滚动视图的内容或容器大小发生变化时，影响滚动视图调整其内容偏移量的角色。

### 管理滚动位置

- **scrollPosition(_:anchor:)**：将滚动位置的绑定与该视图中的滚动视图关联。
- **scrollPosition(id:anchor:)**：在该视图中的滚动视图滚动时关联要更新的绑定。
- **defaultScrollAnchor(_:)**：关联一个锚点，用于控制默认情况下应渲染滚动视图内容的哪一部分。
- **defaultScrollAnchor(_:for:)**：关联锚点以控制特定情况下滚动视图的位置。
- **ScrollPosition**：定义滚动视图在其内容中滚动的语义位置的类型。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/ScrollAnchorRole
crawled: 2025-12-02T17:40:17Z
---

# ScrollAnchorRole

**Structure**

A type defining the role of a scroll anchor.

## Declaration

```swift
struct ScrollAnchorRole
```

## Overview

You can associate a [UnitPoint](UnitPoint.zh-Hans.md) to a [ScrollView](ScrollView.zh-Hans.md) using the [defaultScrollAnchor(_:)](View/defaultScrollAnchor.zh-Hans.md) modifier. By default, the system uses this point for different kinds of behaviors including:

- Where the scroll view should initially be scrolled
- How the scroll view should handle content size or container size changes
- How the scroll view should align content smaller than its container size

You can further customize this behavior by assigning different unit points for these different roles.

## Type Properties

- **alignment**: The role that influences how a scroll view should align its content when the size of its content is smaller than the container size of the scroll view.
- **initialOffset**: The role that influences where a scroll view should be initially scrolled.
- **sizeChanges**: The role that influences how a scroll view should adjust its content offset when the scroll view’s content or container size changes.

## Managing scroll position

- **scrollPosition(_:anchor:)**: Associates a binding to a scroll position with a scroll view within this view.
- **scrollPosition(id:anchor:)**: Associates a binding to be updated when a scroll view within this view scrolls.
- **defaultScrollAnchor(_:)**: Associates an anchor to control which part of the scroll view’s content should be rendered by default.
- **defaultScrollAnchor(_:for:)**: Associates an anchor to control the position of a scroll view in a particular circumstance.
- **ScrollPosition**: A type that defines the semantic position of where a scroll view is scrolled within its content.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

