--- 来源：https://developer.apple.com/documentation/swiftui/transition
抓取时间：2025-12-04T13:16:09Z

---

# 过渡

**Protocol**

描述视图添加到视图层级结构或从中移除时要应用的视图更改。

## 声明

```swift
@MainActor @preconcurrency protocol Transition
```

## 概述

过渡通常通过对 `content` 应用一个或多个修饰符来实现。对于对称过渡，可以使用 `phase` 上的 `isIdentity` 属性来更改修饰符的属性。对于非对称过渡，可以使用阶段本身来更改这些属性。过渡效果不应在 `content` 上使用任何影响身份的更改，例如 `.id`、`if` 和 `switch`，因为这样做会重置应用这些更改的视图的状态，导致工作浪费，并在视图出现和消失时产生意想不到的行为。

以下代码定义了一个过渡效果，可用于在视图出现和消失时更改其不透明度和旋转角度。

```swift
struct RotatingFadeTransition: Transition {
    func body(content: Content, phase: TransitionPhase) -> some View {
        content
          .opacity(phase.isIdentity ? 1.0 : 0.0)
          .rotationEffect(phase.rotation)
    }
}
extension TransitionPhase {
    fileprivate var rotation: Angle {
        switch self {
        case .willAppear: return .degrees(30)
        case .identity: return .zero
        case .didDisappear: return .degrees(-30)
        }
    }
}
```

如果符合此协议的类型在其基本声明中包含该协议，则该类型将从协议继承隔离性：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下隔离到主要参与者，但这不是必需的。在扩展中声明一致性以选择退出主 Actor 隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

- 另请参阅：`TransitionPhase`

- 另请参阅：`AnyTransition`

## 获取内置过渡效果

- **blurReplace**：一种通过结合模糊和缩放效果来动画化视图插入或移除的过渡效果。

- **blurReplace(_:)**：一种通过结合模糊和缩放效果来动画化视图插入或移除的过渡效果。

- **identity**：一种将输入视图原封不动地作为输出视图返回的过渡效果。

- **move(edge:)**：返回一种将视图移开并朝向视图指定边缘的过渡效果。

- **offset(_:)**：返回一个将视图偏移指定距离的过渡效果。

- **offset(x:y:)**：返回一个将视图偏移指定 x 和 y 值的过渡效果。

- **opacity**：插入时从透明变为不透明，移除时从不透明变为透明的过渡效果。

- **push(from:)**：创建一个过渡效果，添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会从另一边缘向外移动并淡出。

- **scale**：返回一个缩放视图的过渡效果。

- **scale(_:anchor:)**：返回一个按指定比例缩放视图的过渡效果。

- **slide**：插入过渡效果，从前缘向内移动；移除过渡效果，从后缘向外移动。

- **symbolEffect**：将默认符号效果过渡应用于插入或移除视图层级结构中的符号图像。其他视图不受此过渡效果影响。

- **symbolEffect(_:options:)**：创建过渡效果，将提供的效果应用于插入或移除视图层级结构中的符号图像。其他视图不受此过渡效果影响。

## 配置过渡效果

- **animation(_:)**：为该过渡效果附加动画。

- **properties**：返回此过渡效果类型的属性。

## 使用过渡效果

- **apply(content:phase:)**

- **combined(with:)**

## 创建自定义过渡效果

- **body(content:phase:)**：获取调用者的当前主体。

- **Body**：表示主体的视图类型。

- **Transition.Content**：传递给 `body()` 的内容视图类型。

## 支持的类型

- **BlurReplaceTransition**：一种通过结合模糊和缩放效果来动画化插入或移除视图的过渡效果。

- **IdentityTransition**：一种将输入视图原封不动地返回为输出视图的过渡效果。

- **MoveTransition**：返回一个将视图向指定边缘移动的过渡效果。

- **OffsetTransition**：返回一个将视图偏移指定距离的过渡效果。

- **OpacityTransition**：插入时从透明变为不透明，移除时从不透明变为透明的过渡效果。

- **PushTransition**：添加到视图后，视图插入时会从指定边缘向内移动并淡入，移除时会向相反边缘向外移动并淡出。

- **ScaleTransition**：返回一个缩放视图的过渡效果。

- **SlideTransition**：插入时从前缘向内移动，移除时向后缘向外移动的过渡效果。

## 定义过渡效果

- **transition(_:)**：将过渡效果与视图关联。

- **TransitionProperties**：`Transition` 可以拥有的属性。

- **TransitionPhase**：指示过渡效果的当前阶段。

- **AsymmetricTransition**：复合过渡效果，插入和删除操作使用不同的过渡效果。

- **AnyTransition**：类型擦除过渡效果。

- **contentTransition(_:)**：修改视图，使其使用指定的过渡效果作为视图内容更改的动画方法。

- **contentTransition**：视图内容的当前动画方法。

- **contentTransitionAddsDrawingGroup**：一个布尔值，用于控制渲染内容过渡的视图是否使用 GPU 加速渲染。

- **ContentTransition**：一种过渡类型，应用于单个视图内的内容，而不是视图的插入或移除。

- **PlaceholderContentView**：用于构造内联修饰符、过渡或其他辅助类型的占位符。

- **navigationTransition(_:)**：设置此视图的导航过渡样式。

- **NavigationTransition**：定义导航到视图时要使用的过渡类型。

- **matchedTransitionSource(id:in:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **matchedTransitionSource(id:in:configuration:)**：将此视图标识为导航过渡（例如缩放过渡）的源。

- **MatchedTransitionSourceConfiguration**：定义匹配过渡源外观的配置。

## 符合规范的类型

- AsymmetricTransition

- BlurReplaceTransition

- IdentityTransition

- MoveTransition

- OffsetTransition

- OpacityTransition

- PushTransition

- ScaleTransition

- SlideTransition

- SymbolEffectTransition


---
source: https://developer.apple.com/documentation/swiftui/transition
crawled: 2025-12-04T13:16:09Z
---

# Transition

**Protocol**

A description of view changes to apply when a view is added to and removed from the view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol Transition
```

## Overview

A transition should generally be made by applying one or more modifiers to the `content`. For symmetric transitions, the `isIdentity` property on `phase` can be used to change the properties of modifiers. For asymmetric transitions, the phase itself can be used to change those properties. Transitions should not use any identity-affecting changes like `.id`, `if`, and `switch` on the `content`, since doing so would reset the state of the view they’re applied to, causing wasted work and potentially surprising behavior when it appears and disappears.

The following code defines a transition that can be used to change the opacity and rotation when a view appears and disappears.

```swift
struct RotatingFadeTransition: Transition {
    func body(content: Content, phase: TransitionPhase) -> some View {
        content
          .opacity(phase.isIdentity ? 1.0 : 0.0)
          .rotationEffect(phase.rotation)
    }
}
extension TransitionPhase {
    fileprivate var rotation: Angle {
        switch self {
        case .willAppear: return .degrees(30)
        case .identity: return .zero
        case .didDisappear: return .degrees(-30)
        }
    }
}
```

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

- See Also: `TransitionPhase`
- See Also: `AnyTransition`

## Getting built-in transitions

- **blurReplace**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **blurReplace(_:)**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **identity**: A transition that returns the input view, unmodified, as the output view.
- **move(edge:)**: Returns a transition that moves the view away, towards the specified edge of the view.
- **offset(_:)**: Returns a transition that offset the view by the specified amount.
- **offset(x:y:)**: Returns a transition that offset the view by the specified x and y values.
- **opacity**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **push(from:)**: Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **scale**: Returns a transition that scales the view.
- **scale(_:anchor:)**: Returns a transition that scales the view by the specified amount.
- **slide**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.
- **symbolEffect**: A transition that applies the default symbol effect transition to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.
- **symbolEffect(_:options:)**: Creates a transition that applies the provided effect to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.

## Configuring a transition

- **animation(_:)**: Attaches an animation to this transition.
- **properties**: Returns the properties this transition type has.

## Using a transition

- **apply(content:phase:)**
- **combined(with:)**

## Creating a custom transition

- **body(content:phase:)**: Gets the current body of the caller.
- **Body**: The type of view representing the body.
- **Transition.Content**: The content view type passed to `body()`.

## Supporting types

- **BlurReplaceTransition**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **IdentityTransition**: A transition that returns the input view, unmodified, as the output view.
- **MoveTransition**: Returns a transition that moves the view away, towards the specified edge of the view.
- **OffsetTransition**: Returns a transition that offset the view by the specified amount.
- **OpacityTransition**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **PushTransition**: A transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **ScaleTransition**: Returns a transition that scales the view.
- **SlideTransition**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.

## Defining transitions

- **transition(_:)**: Associates a transition with the view.
- **TransitionProperties**: The properties a `Transition` can have.
- **TransitionPhase**: An indication of which the current stage of a transition.
- **AsymmetricTransition**: A composite `Transition` that uses a different transition for insertion versus removal.
- **AnyTransition**: A type-erased transition.
- **contentTransition(_:)**: Modifies the view to use a given transition as its method of animating changes to the contents of its views.
- **contentTransition**: The current method of animating the contents of views.
- **contentTransitionAddsDrawingGroup**: A Boolean value that controls whether views that render content transitions use GPU-accelerated rendering.
- **ContentTransition**: A kind of transition that applies to the content within a single view, rather than to the insertion or removal of a view.
- **PlaceholderContentView**: A placeholder used to construct an inline modifier, transition, or other helper type.
- **navigationTransition(_:)**: Sets the navigation transition style for this view.
- **NavigationTransition**: A type that defines the transition to use when navigating to a view.
- **matchedTransitionSource(id:in:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **matchedTransitionSource(id:in:configuration:)**: Identifies this view as the source of a navigation transition, such as a zoom transition.
- **MatchedTransitionSourceConfiguration**: A configuration that defines the appearance of a matched transition source.

## Conforming Types

- AsymmetricTransition
- BlurReplaceTransition
- IdentityTransition
- MoveTransition
- OffsetTransition
- OpacityTransition
- PushTransition
- ScaleTransition
- SlideTransition
- SymbolEffectTransition

