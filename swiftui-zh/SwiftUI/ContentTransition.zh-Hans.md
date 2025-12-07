---
来源： https://developer.apple.com/documentation/SwiftUI/ContentTransition
抓取时间：2025-12-02T17:34:26Z
---

# 内容转换

**Structure**

一种适用于单个视图中的内容，而非插入或移除视图的过渡。

## 声明

```swift
struct ContentTransition
```

## 概览

使用[contentTransition(_:)](View/contentTransition.zh-Hans.md)修饰符设置视图中内容转换的行为，并传递一个已定义的转换，如[opacity](ContentTransition/opacity.zh-Hans.md) 或 [interpolate](ContentTransition/interpolate.zh-Hans.md) 作为参数。



内容转换只在[Animation](Animation.zh-Hans.md) 块的上下文中生效。

## 获取内容转换

- **identity**：身份内容转换，表示内容变化不应动画化。
- **interpolate**：内容转换，表示视图在适当的情况下尝试在转换过程中插入其内容。
- **numericText(countsDown:)**：创建一个内容转换，用于显示数字文本的`Text` 视图。在某些环境中，对文本的更改将启用专为向上或向下计数的数字字符定制的非标准过渡。
- **numericText(value:)**：创建用于`Text` 显示数字的视图的内容过渡。
- **opacity**：内容过渡，表示插入时内容从透明渐变为不透明，移除时从不透明渐变为透明。
- **symbolEffect**：内容转换，可将默认的符号效果转换应用于插入或移除视图层次结构中的符号图像。其他视图不受此过渡的影响。
- **symbolEffect(_:options:)**：创建一个内容转换，将符号替换动画应用到它所应用的符号图像。

## 定义过渡

- **transition(_:)**：将转换与视图关联。
- **Transition**：当视图添加到视图层次结构或从视图层次结构中移除视图时要应用的视图更改描述。
- **TransitionProperties**：`Transition`可具有的属性。
- **TransitionPhase**：表示过渡的当前阶段。
- **AsymmetricTransition**：复合`Transition`，插入与移除使用不同的转换。
- **AnyTransition**：类型抹除的转换。
- **contentTransition(_:)**：修改视图，使其使用给定的转换作为其视图内容变化的动画方法。
- **contentTransition**：视图内容的当前动画方法。
- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容转换的视图是否使用 GPU 加速渲染。
- **PlaceholderContentView**：用于构建内联修饰符、转换或其他辅助类型的占位符。
- **navigationTransition(_:)**：为该视图设置导航过渡样式。
- **NavigationTransition**：定义导航到视图时使用的过渡类型。
- **matchedTransitionSource(id:in:)**：将此视图标识为导航转换（如缩放转换）的源。
- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航转换（如缩放转换）的源。
- **MatchedTransitionSourceConfiguration**：定义匹配转换源外观的配置。

## 符合

- 等价
- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/ContentTransition
crawled: 2025-12-02T17:34:26Z
---

# ContentTransition

**Structure**

A kind of transition that applies to the content within a single view, rather than to the insertion or removal of a view.

## Declaration

```swift
struct ContentTransition
```

## Overview

Set the behavior of content transitions within a view with the [contentTransition(_:)](View/contentTransition.zh-Hans.md) modifier, passing in one of the defined transitions, such as [opacity](ContentTransition/opacity.zh-Hans.md) or [interpolate](ContentTransition/interpolate.zh-Hans.md) as the parameter.



Content transitions only take effect within the context of an [Animation](Animation.zh-Hans.md) block.

## Getting content transitions

- **identity**: The identity content transition, which indicates that content changes shouldn’t animate.
- **interpolate**: A content transition that indicates the views attempt to interpolate their contents during transitions, where appropriate.
- **numericText(countsDown:)**: Creates a content transition intended to be used with `Text` views displaying numeric text. In certain environments changes to the text will enable a nonstandard transition tailored to numeric characters that count up or down.
- **numericText(value:)**: Creates a content transition intended to be used with `Text` views displaying numbers.
- **opacity**: A content transition that indicates content fades from transparent to opaque on insertion, and from opaque to transparent on removal.
- **symbolEffect**: A content transition that applies the default symbol effect transition to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.
- **symbolEffect(_:options:)**: Creates a content transition that applies the symbol Replace animation to symbol images that it is applied to.

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **Transition**: A description of view changes to apply when a view is added to and removed from the view hierarchy.
- **TransitionProperties**: The properties a `Transition` can have.
- **TransitionPhase**: An indication of which the current stage of a transition.
- **AsymmetricTransition**: A composite `Transition` that uses a different transition for insertion versus removal.
- **AnyTransition**: A type-erased transition.
- **contentTransition(_:)**: Modifies the view to use a given transition as its method of animating changes to the contents of its views.
- **contentTransition**: The current method of animating the contents of views.
- **contentTransitionAddsDrawingGroup**: A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.
- **PlaceholderContentView**: A placeholder used to construct an inline modifier, transition, or other helper type.
- **navigationTransition(_:)**: Sets the navigation transition style for this view.
- **NavigationTransition**: A type that defines the transition to use when navigating to a view.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

