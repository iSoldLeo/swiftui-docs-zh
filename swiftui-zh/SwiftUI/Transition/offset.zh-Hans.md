---
来源： https://developer.apple.com/documentation/SwiftUI/Transition/offset(_:)
抓取时间： 2025-12-01T11:05:13Z
---

# offset(_:)

**类型方法**

返回视图偏移指定量的转换。

## 声明

```swift
@MainActor @preconcurrency static func offset(_ offset: CGSize) -> Self
```

## 获取内置过渡

- **blurReplace**：结合模糊和缩放效果，以动画方式插入或移除视图的过渡效果。
- **blurReplace(_:)**：结合模糊和缩放效果，以动画方式插入或移除视图的转场。
- **identity**：将未修改的输入视图作为输出视图返回的变换。
- **move(edge:)**：返回一个将视图移向指定视图边缘的变换。
- **offset(x:y:)**：返回将视图偏移指定 x 和 y 值的过渡。
- **opacity**：插入时从透明到不透明，移除时从不透明到透明的过渡。
- **push(from:)**：创建一个过渡效果，添加到视图后，将通过从指定边缘向内移动视图并使其逐渐变暗来使插入视图成为动画，以及通过向相反边缘移动视图并使其逐渐变暗来使移除视图成为动画。
- **scale**：返回缩放视图的过渡效果。
- **scale(_:anchor:)**：返回按指定大小缩放视图的变换。
- **slide**：通过从前缘移入来插入，并通过向后缘移出来移除的过渡。
- **symbolEffect**：将默认符号效果过渡应用于插入或移除视图层次结构中的符号图像的过渡。其他视图不受此过渡的影响。
- **symbolEffect(_:options:)**：创建一个过渡，将提供的效果应用到插入或移除的视图层次结构中的符号图像。其他视图不受此过渡的影响。


---
source: https://developer.apple.com/documentation/SwiftUI/Transition/offset(_:)
crawled: 2025-12-01T11:05:13Z
---

# offset(_:)

**Type Method**

Returns a transition that offset the view by the specified amount.

## Declaration

```swift
@MainActor @preconcurrency static func offset(_ offset: CGSize) -> Self
```

## Getting built-in transitions

- **blurReplace**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **blurReplace(_:)**: A transition that animates the insertion or removal of a view by combining blurring and scaling effects.
- **identity**: A transition that returns the input view, unmodified, as the output view.
- **move(edge:)**: Returns a transition that moves the view away, towards the specified edge of the view.
- **offset(x:y:)**: Returns a transition that offset the view by the specified x and y values.
- **opacity**: A transition from transparent to opaque on insertion, and from opaque to transparent on removal.
- **push(from:)**: Creates a transition that when added to a view will animate the view’s insertion by moving it in from the specified edge while fading it in, and animate its removal by moving it out towards the opposite edge and fading it out.
- **scale**: Returns a transition that scales the view.
- **scale(_:anchor:)**: Returns a transition that scales the view by the specified amount.
- **slide**: A transition that inserts by moving in from the leading edge, and removes by moving out towards the trailing edge.
- **symbolEffect**: A transition that applies the default symbol effect transition to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.
- **symbolEffect(_:options:)**: Creates a transition that applies the provided effect to symbol images within the inserted or removed view hierarchy. Other views are unaffected by this transition.

