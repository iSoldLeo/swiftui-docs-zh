--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:)

抓取时间：2025-12-03T06:13:21Z

---

# buildPartialBlock(accumulated:next:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildPartialBlock(accumulated:next:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- buildPartialBlock(accumulated:next:) 

类型 方法# buildPartialBlock(accumulated:next:)

iOS 17.0+、iPadOS 17.0+、Mac Catalyst 17.0+、macOS 14.0+、tvOS 17.0+、vSOS 1.0+、watchOS 10.0+

```
static func buildPartialBlock(
    accumulated: some KeyframeTrackContent<Value>,
    next: some KeyframeTrackContent<Value>
) -> some KeyframeTrackContent<Value>

```

## [参见另请参阅](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:)#see-also)

### [构建关键帧轨道内容](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:)#Building-keyframe-track-content)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)来自结果构建器的条件结果。

---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:)
crawled: 2025-12-03T06:13:21Z
---

# buildPartialBlock(accumulated:next:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildPartialBlock(accumulated:next:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

-  buildPartialBlock(accumulated:next:) 

Type Method# buildPartialBlock(accumulated:next:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildPartialBlock(
    accumulated: some KeyframeTrackContent<Value>,
    next: some KeyframeTrackContent<Value>
) -> some KeyframeTrackContent<Value>

```

## [See Also](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:)#see-also)

### [Building keyframe track content](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(accumulated:next:)#Building-keyframe-track-content)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)A conditional result from the result builder.