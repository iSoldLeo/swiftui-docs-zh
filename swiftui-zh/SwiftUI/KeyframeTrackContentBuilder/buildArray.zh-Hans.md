--- 来源：https://developer.apple.com/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:)

抓取时间：2025-12-04T13:14:34Z

---

# buildArray(_:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildArray(_:) ](/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- buildArray(_:) 

类型 方法# buildArray(_:)

iOS 17.0+、iPadOS 17.0+、Mac Catalyst 17.0+、macOS 14.0+、tvOS 17.0+、vVOS 1.0+、watchOS 10.0+

```
static func buildArray(_ components: [some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>

```

## [另请参阅](/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:)#see-also)

### [构建关键帧轨道]内容](/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:)#构建关键帧轨道内容)

`static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)结果构建器的条件结果。

---
source: https://developer.apple.com/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:)
crawled: 2025-12-04T13:14:34Z
---

# buildArray(_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildArray(_:) ](/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

-  buildArray(_:) 

Type Method# buildArray(_:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildArray(_ components: [some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>

```

## [See Also](/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:)#see-also)

### [Building keyframe track content](/documentation/swiftui/keyframetrackcontentbuilder/buildarray(_:)#Building-keyframe-track-content)

`static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)A conditional result from the result builder.