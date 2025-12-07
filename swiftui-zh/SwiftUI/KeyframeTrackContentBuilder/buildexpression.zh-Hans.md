--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:)

抓取时间：2025-12-01T11:02:25Z

---

# buildExpression(_:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildExpression(_:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- buildExpression(_:) 

类型 方法# buildExpression(_:)

iOS 17.0+、iPadOS 17.0+、Mac Catalyst 17.0+、macOS 14.0+、tvOS 17.0+、vVOS 1.0+、watchOS 10.0+

```
static func buildExpression<K>(_ expression: K) -> K where Value == K.Value, K : KeyframeTrackContent
```

## [另请参阅](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:)#see-also)

### [构建关键帧轨道]内容](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:)#构建关键帧轨道内容)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)来自结果构建器的条件结果。

---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:)
crawled: 2025-12-01T11:02:25Z
---

# buildExpression(_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildExpression(_:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

-  buildExpression(_:) 

Type Method# buildExpression(_:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildExpression<K>(_ expression: K) -> K where Value == K.Value, K : KeyframeTrackContent
```

## [See Also](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:)#see-also)

### [Building keyframe track content](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildExpression(_:)#Building-keyframe-track-content)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(second:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)A conditional result from the result builder.