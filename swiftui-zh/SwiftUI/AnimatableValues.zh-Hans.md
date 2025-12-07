---
来源： https://developer.apple.com/documentation/SwiftUI/AnimatableValues
抓取时间： 2025-12-02T17:34:10Z
---

# AnimatableValues | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ AnimatableValues ](/documentation/SwiftUI/AnimatableValues)

- 动画值

结构# AnimatableValues

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+tvOS 26.0+visionOS 26.0+watchOS 26.0+

```
@frozen
struct AnimatableValues<each Value> where repeat each Value : VectorArithmetic
```

## [主题](/documentation/SwiftUI/AnimatableValues#topics)

### [Initializers](/documentation/SwiftUI/AnimatableValues#Initializers)

[`init(repeat each Value)`](/documentation/swiftui/animatablevalues/init(_:))Creates a tuple of animatable values.### [Instance Properties](/documentation/SwiftUI/AnimatableValues#Instance-Properties)

[`var magnitudeSquared: Double`](/documentation/swiftui/animatablevalues/magnitudesquared)动画值元组与自身的点积。 [`var value: (repeat each Value)`](/documentation/swiftui/animatablevalues/value)值元组。

### [符合](/documentation/SwiftUI/AnimatableValues#conforms-to)

- [⟦ic_0008⟧](⟦lu_0020⟧)

- [⟦ic_0007⟧](⟦lu_0019⟧)

- [⟦ic_0006⟧](⟦lu_0018⟧)

## [See Also](/documentation/SwiftUI/AnimatableValues#see-also)

### [使数据动画化](/documentation/SwiftUI/AnimatableValues#Making-data-animatable)

[`protocol Animatable`](/documentation/swiftui/animatable)描述如何使视图属性动画化的类型。[`protocol VectorArithmetic`](/documentation/swiftui/vectorarithmetic)一个可以作为可动画类型的可动画数据的类型。

---
source: https://developer.apple.com/documentation/SwiftUI/AnimatableValues
crawled: 2025-12-02T17:34:10Z
---

# AnimatableValues | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ AnimatableValues ](/documentation/SwiftUI/AnimatableValues)

-  AnimatableValues 

Structure# AnimatableValues

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+tvOS 26.0+visionOS 26.0+watchOS 26.0+

```
@frozen
struct AnimatableValues<each Value> where repeat each Value : VectorArithmetic
```

## [Topics](/documentation/SwiftUI/AnimatableValues#topics)

### [Initializers](/documentation/SwiftUI/AnimatableValues#Initializers)

[`init(repeat each Value)`](/documentation/swiftui/animatablevalues/init(_:))Creates a tuple of animatable values.### [Instance Properties](/documentation/SwiftUI/AnimatableValues#Instance-Properties)

[`var magnitudeSquared: Double`](/documentation/swiftui/animatablevalues/magnitudesquared)The dot-product of the tuple of animatable values with itself.[`var value: (repeat each Value)`](/documentation/swiftui/animatablevalues/value)The tuple of values.## [Relationships](/documentation/SwiftUI/AnimatableValues#relationships)

### [Conforms To](/documentation/SwiftUI/AnimatableValues#conforms-to)

- [`AdditiveArithmetic`](/documentation/Swift/AdditiveArithmetic)

- [`Equatable`](/documentation/Swift/Equatable)

- [`VectorArithmetic`](/documentation/swiftui/vectorarithmetic)

## [See Also](/documentation/SwiftUI/AnimatableValues#see-also)

### [Making data animatable](/documentation/SwiftUI/AnimatableValues#Making-data-animatable)

[`protocol Animatable`](/documentation/swiftui/animatable)A type that describes how to animate a property of a view.[`struct AnimatablePair`](/documentation/swiftui/animatablepair)A pair of animatable values, which is itself animatable.[`protocol VectorArithmetic`](/documentation/swiftui/vectorarithmetic)A type that can serve as the animatable data of an animatable type.[`struct EmptyAnimatableData`](/documentation/swiftui/emptyanimatabledata)An empty type for animatable data.