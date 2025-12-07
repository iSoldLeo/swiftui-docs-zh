--- 来源：https://developer.apple.com/documentation/SwiftUI/Scroll-views

抓取时间：2025-12-02T17:38:27Z

---

# 滚动视图

**API 集合**

使用户能够滚动查看当前显示空间不足的内容。

## 概述

当视图内容无法完整显示在屏幕上时，您可以将视图包裹在 [ScrollView](ScrollView.zh-Hans.md) 中，使用户能够在一个或多个轴上滚动。使用视图修饰符配置滚动视图。例如，您可以设置滚动指示器的可见性或特定维度的滚动功能。

您可以将任何类型的视图放入滚动视图中，但滚动视图最常用于元素过多而无法完整显示在屏幕上的布局容器。对于某些放入滚动视图中的容器视图（例如延迟加载的堆栈），容器只有在视图可见或几乎可见时才会加载它们。对于其他类型的容器，例如常规的堆叠式和网格式容器，无论滚动状态如何，容器都会一次性加载所有内容。

[Lists](Lists.zh-Hans.md) 和 [Tables](Tables.zh-Hans.md) 隐式包含滚动视图，因此您无需为这些容器类型添加滚动功能。但是，您可以使用与显式滚动视图相同的视图修饰符来配置它们的隐式滚动视图。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/scroll-views]。

## 创建滚动视图

- **ScrollView**：可滚动视图。

- **ScrollViewReader**：通过与代理配合滚动到已知子视图，从而提供程序化滚动的视图。

- **ScrollViewProxy**：支持在视图层次结构中对可滚动视图进行程序化滚动的代理值。

## 管理滚动位置

- **scrollPosition(_:anchor:)**：将一个绑定到滚动位置的属性关联到此视图内的滚动视图。

- **scrollPosition(id:anchor:)**：关联一个绑定，当此视图内的滚动视图滚动时，该绑定将被更新。

- **defaultScrollAnchor(_:)**：关联一个锚点，用于控制默认情况下应渲染滚动视图内容的哪一部分。

- **defaultScrollAnchor(_:for:)**：关联一个锚点，用于控制滚动视图在特定情况下的位置。

- **ScrollAnchorRole**：定义滚动锚点角色的类型。

- **ScrollPosition**：定义滚动视图在其内容中滚动的语义位置的类型。

## 定义滚动目标

- **scrollTargetBehavior(_:)**：设置可沿指定轴滚动的视图的滚动行为。

- **scrollTargetLayout(isEnabled:)**：将最外层布局配置为滚动目标布局。

- **ScrollTarget**：定义滚动视图尝试滚动到的目标类型。

- **ScrollTargetBehavior**：定义可滚动视图的滚动行为类型。

- **ScrollTargetBehaviorContext**：滚动目标行为更新其滚动目标的上下文。

- **PagingScrollTargetBehavior**：将滚动目标与基于容器的几何体对齐的滚动行为。

- **ViewAlignedScrollTargetBehavior**：将滚动目标与基于视图的几何体对齐的滚动行为。

- **AnyScrollTargetBehavior**：类型擦除后的滚动目标行为。

- **ScrollTargetBehaviorProperties**：影响滚动目标行为所应用的滚动视图的属性。

- **ScrollTargetBehaviorPropertiesContext**：滚动目标行为可以决定其属性的上下文。

## 滚动过渡动画

- **scrollTransition(_:axis:transition:)**：应用给定的过渡动画，当此视图在包含它的滚动视图的可见区域内出现和消失时，在过渡的各个阶段之间进行动画处理。

- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**：应用给定的过渡动画，当此视图在包含它的滚动视图的可见区域内出现和消失时，在过渡的各个阶段之间进行动画处理。

- **ScrollTransitionPhase**：视图在其他视图之间滚动时所经历的过渡阶段。

- **ScrollTransitionConfiguration**：滚动过渡的配置，用于控制当视图滚动通过包含滚动视图或其他容器的可见区域时，过渡效果的应用方式。

## 响应滚动视图的变化

- **onScrollGeometryChange(for:of:action:)**：添加一个操作，当由滚动几何体创建的值发生变化时执行该操作。

- **onScrollTargetVisibilityChange(idType:threshold:_:)**：添加一个操作，用于调用有关哪些视图被视为可见的信息。

- **onScrollVisibilityChange(threshold:_:)**：添加一个操作，当视图跨越阈值以被视为屏幕显示/隐藏时执行该操作。

- **onScrollPhaseChange(_:)**：添加一个操作，当层次结构中第一个滚动视图的滚动阶段发生变化时执行该操作。

- **ScrollGeometry**：定义滚动视图几何体的类型。

- **ScrollPhase**：描述可滚动视图（例如滚动视图）滚动手势状态的类型。

- **ScrollPhaseChangeContext**：当滚动视图的阶段发生变化时，提供更多内容的类型。

## 显示滚动指示器

- **scrollIndicatorsFlash(onAppear:)**：当可滚动视图出现时，闪烁其滚动指示器。

- **scrollIndicatorsFlash(trigger:)**：当值发生变化时，闪烁可滚动视图的滚动指示器。

- **scrollIndicators(_:axes:)**：设置此视图中滚动指示器的可见性。

- **horizontalScrollIndicatorVisibility**：应用于任何水平滚动内容的滚动指示器的可见性。

- **verticalScrollIndicatorVisibility**：应用于任何垂直滚动内容的滚动指示器的可见性。

- **ScrollIndicatorVisibility**：UI元素滚动指示器的可见性。

## 管理内容可见性

- **scrollContentBackground(_:)**：指定此视图中可滚动视图的背景可见性。

- **scrollClipDisabled(_:)**：设置滚动视图是否将其内容裁剪到边界内。

- **ScrollContentOffsetAdjustmentBehavior**：定义滚动视图可以具有的不同内容偏移调整行为的类型。

## 禁用滚动

- **scrollDisabled(_:)**：禁用或启用可滚动视图中的滚动。

- **isScrollEnabled**：布尔值，指示与此环境关联的任何滚动视图是否允许滚动。

## 配置滚动回弹行为

- **scrollBounceBehavior(_:axes:)**：配置可滚动视图沿指定轴的回弹行为。

- **horizontalScrollBounceBehavior**：可滚动视图水平轴的滚动回弹模式。

- **verticalScrollBounceBehavior**：可滚动视图垂直轴的滚动回弹模式。

- **ScrollBounceBehavior**：可滚动视图到达内容末尾时的回弹方式。

## 配置滚动边缘效果

- **scrollEdgeEffectStyle(_:for:)**：配置此层级结构中滚动视图的滚动边缘效果样式。

- **scrollEdgeEffectHidden(_:for:)**：隐藏此层级结构中滚动视图的所有滚动边缘效果。

- **ScrollEdgeEffectStyle**：定义滚动视图的凹槽样式的结构体。

- **safeAreaBar(edge:alignment:spacing:content:)**：在修改后的视图旁边显示指定内容作为自定义栏。

## 与软件键盘交互

- **scrollDismissesKeyboard(_:)**：配置可滚动内容与软件键盘的交互行为。

- **scrollDismissesKeyboardMode**：可滚动内容与软件键盘的交互方式。

- **ScrollDismissesKeyboardMode**：可滚动内容与软件键盘交互的方式。

## 管理不同输入方式的滚动

- **scrollInputBehavior(_:for:)**：启用或禁用使用特定输入方式时可滚动视图的滚动功能。

- **ScrollInputKind**：用于滚动视图的输入方式。

- **ScrollInputBehavior**：定义输入方式是否应滚动视图的类型。

## 视图布局

- **布局基础**：在内置布局容器（例如堆栈和网格）中排列视图。

- **布局调整**：对对齐方式、间距、内边距和其他布局参数进行微调。

- **自定义布局**：以自定义方式放置视图，并在布局类型之间创建动画过渡效果。

- **Lists**：显示结构化的、可滚动的信息列。

- **Tables**：显示以行和列排列的、可选择和可排序的数据。

- **视图分组**：在不同类型的、用途明确的容器（例如窗体或控件组）中呈现视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Scroll-views
crawled: 2025-12-02T17:38:27Z
---

# Scroll views

**API Collection**

Enable people to scroll to content that doesn’t fit in the current display.

## Overview

When the content of a view doesn’t fit in the display, you can wrap the view in a [ScrollView](ScrollView.zh-Hans.md) to enable people to scroll on one or more axes. Configure the scroll view using view modifiers. For example, you can set the visibility of the scroll indicators or the availability of scrolling in a given dimension.



You can put any view type in a scroll view, but you most often use a scroll view for a layout container with too many elements to fit in the display. For some container views that you put in a scroll view, like lazy stacks, the container doesn’t load views until they are visible or almost visible. For others, like regular stacks and grids, the container loads the content all at once, regardless of the state of scrolling.

[Lists](Lists.zh-Hans.md) and [Tables](Tables.zh-Hans.md) implicitly include a scroll view, so you don’t need to add scrolling to those container types. However, you can configure their implicit scroll views with the same view modifiers that apply to explicit scroll views.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/scroll-views] in the Human Interface Guidelines.

## Creating a scroll view

- **ScrollView**: A scrollable view.
- **ScrollViewReader**: A view that provides programmatic scrolling, by working with a proxy to scroll to known child views.
- **ScrollViewProxy**: A proxy value that supports programmatic scrolling of the scrollable views within a view hierarchy.

## Managing scroll position

- **scrollPosition(_:anchor:)**: Associates a binding to a scroll position with a scroll view within this view.
- **scrollPosition(id:anchor:)**: Associates a binding to be updated when a scroll view within this view scrolls.
- **defaultScrollAnchor(_:)**: Associates an anchor to control which part of the scroll view’s content should be rendered by default.
- **defaultScrollAnchor(_:for:)**: Associates an anchor to control the position of a scroll view in a particular circumstance.
- **ScrollAnchorRole**: A type defining the role of a scroll anchor.
- **ScrollPosition**: A type that defines the semantic position of where a scroll view is scrolled within its content.

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
- **ScrollTargetBehaviorPropertiesContext**: The context in which a scroll target behavior can decide its properties.

## Animating scroll transitions

- **scrollTransition(_:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **scrollTransition(topLeading:bottomTrailing:axis:transition:)**: Applies the given transition, animating between the phases of the transition as this view appears and disappears within the visible region of the containing scroll view.
- **ScrollTransitionPhase**: The phases that a view transitions between when it scrolls among other views.
- **ScrollTransitionConfiguration**: The configuration of a scroll transition that controls how a transition is applied as a view is scrolled through the visible region of a containing scroll view or other container.

## Responding to scroll view changes

- **onScrollGeometryChange(for:of:action:)**: Adds an action to be performed when a value, created from a scroll geometry, changes.
- **onScrollTargetVisibilityChange(idType:threshold:_:)**: Adds an action to be called with information about what views would be considered visible.
- **onScrollVisibilityChange(threshold:_:)**: Adds an action to be called when the view crosses the threshold to be considered on/off screen.
- **onScrollPhaseChange(_:)**: Adds an action to perform when the scroll phase of the first scroll view in the hierarchy changes.
- **ScrollGeometry**: A type that defines the geometry of a scroll view.
- **ScrollPhase**: A type that describes the state of a scroll gesture of a scrollable view like a scroll view.
- **ScrollPhaseChangeContext**: A type that provides you with more content when the phase of a scroll view changes.

## Showing scroll indicators

- **scrollIndicatorsFlash(onAppear:)**: Flashes the scroll indicators of a scrollable view when it appears.
- **scrollIndicatorsFlash(trigger:)**: Flashes the scroll indicators of scrollable views when a value changes.
- **scrollIndicators(_:axes:)**: Sets the visibility of scroll indicators within this view.
- **horizontalScrollIndicatorVisibility**: The visibility to apply to scroll indicators of any horizontally scrollable content.
- **verticalScrollIndicatorVisibility**: The visiblity to apply to scroll indicators of any vertically scrollable content.
- **ScrollIndicatorVisibility**: The visibility of scroll indicators of a UI element.

## Managing content visibility

- **scrollContentBackground(_:)**: Specifies the visibility of the background for scrollable views within this view.
- **scrollClipDisabled(_:)**: Sets whether a scroll view clips its content to its bounds.
- **ScrollContentOffsetAdjustmentBehavior**: A type that defines the different kinds of content offset adjusting behaviors a scroll view can have.

## Disabling scrolling

- **scrollDisabled(_:)**: Disables or enables scrolling in scrollable views.
- **isScrollEnabled**: A Boolean value that indicates whether any scroll views associated with this environment allow scrolling to occur.

## Configuring scroll bounce behavior

- **scrollBounceBehavior(_:axes:)**: Configures the bounce behavior of scrollable views along the specified axis.
- **horizontalScrollBounceBehavior**: The scroll bounce mode for the horizontal axis of scrollable views.
- **verticalScrollBounceBehavior**: The scroll bounce mode for the vertical axis of scrollable views.
- **ScrollBounceBehavior**: The ways that a scrollable view can bounce when it reaches the end of its content.

## Configuring scroll edge effects

- **scrollEdgeEffectStyle(_:for:)**: Configures the scroll edge effect style for scroll views within this hierarchy.
- **scrollEdgeEffectHidden(_:for:)**: Hides any scroll edge effects for scroll views within this hierarchy.
- **ScrollEdgeEffectStyle**: A structure that defines the style of pocket a scroll view will have.
- **safeAreaBar(edge:alignment:spacing:content:)**: Shows the specified content as a custom bar beside the modified view.

## Interacting with a software keyboard

- **scrollDismissesKeyboard(_:)**: Configures the behavior in which scrollable content interacts with the software keyboard.
- **scrollDismissesKeyboardMode**: The way that scrollable content interacts with the software keyboard.
- **ScrollDismissesKeyboardMode**: The ways that scrollable content can interact with the software keyboard.

## Managing scrolling for different inputs

- **scrollInputBehavior(_:for:)**: Enables or disables scrolling in scrollable views when using particular inputs.
- **ScrollInputKind**: Inputs used to scroll views.
- **ScrollInputBehavior**: A type that defines whether input should scroll a view.

## View layout

- **Layout fundamentals**: Arrange views inside built-in layout containers like stacks and grids.
- **Layout adjustments**: Make fine adjustments to alignment, spacing, padding, and other layout parameters.
- **Custom layout**: Place views in custom arrangements and create animated transitions between layout types.
- **Lists**: Display a structured, scrollable column of information.
- **Tables**: Display selectable, sortable data arranged in rows and columns.
- **View groupings**: Present views in different kinds of purpose-driven containers, like forms or control groups.

