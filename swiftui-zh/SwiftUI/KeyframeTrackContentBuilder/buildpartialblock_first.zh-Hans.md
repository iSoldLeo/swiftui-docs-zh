--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:)

抓取时间：2025-12-03T06:13:28Z

---

# buildPartialBlock(first:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildPartialBlock(first:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- buildPartialBlock(first:) 

类型 方法# buildPartialBlock(first:)

iOS 17.0+、iPadOS 17.0+、Mac Catalyst 17.0+、macOS 14.0+、tvOS 17.0+、visionOS 1.0+、watchOS 10.0+

```
static func buildPartialBlock<K>(first: K) -> K where Value == K.Value, K : KeyframeTrackContent
```

## [另请参阅](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:)#see-also)

### [构建关键帧轨道]内容](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:)#构建关键帧轨道内容)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)结果构建器的条件结果。

---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:)
crawled: 2025-12-03T06:13:28Z
---

# buildPartialBlock(first:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildPartialBlock(first:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

-  buildPartialBlock(first:) 

Type Method# buildPartialBlock(first:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildPartialBlock<K>(first: K) -> K where Value == K.Value, K : KeyframeTrackContent
```

## [See Also](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:)#see-also)

### [Building keyframe track content](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildPartialBlock(first:)#Building-keyframe-track-content)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)A conditional result from the result builder.