--- 来源：https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:)

抓取时间：2025-12-01T11:02:18Z

---

# buildEither(second:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildEither(second:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- buildEither(second:) 

类型 方法# buildEither(second:)

iOS 17.0+、iPadOS 17.0+、Mac Catalyst 17.0+、macOS 14.0+、tvOS 17.0+、vSOS 1.0+、watchOS 10.0+

```
static func buildEither<First, Second>(second component: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second> where Value == First.Value, First : KeyframeTrackContent, Second : KeyframeTrackContent, First.Value == Second.Value
```

## [另请参阅](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:)#see-also)

### [构建关键帧轨道]内容](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:)#构建关键帧轨道内容)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)来自结果构建器的条件结果。

---
source: https://developer.apple.com/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:)
crawled: 2025-12-01T11:02:18Z
---

# buildEither(second:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

- [ buildEither(second:) ](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:))

- [ KeyframeTrackContentBuilder ](/documentation/swiftui/keyframetrackcontentbuilder)

-  buildEither(second:) 

Type Method# buildEither(second:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildEither<First, Second>(second component: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second> where Value == First.Value, First : KeyframeTrackContent, Second : KeyframeTrackContent, First.Value == Second.Value
```

## [See Also](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:)#see-also)

### [Building keyframe track content](/documentation/SwiftUI/KeyframeTrackContentBuilder/buildEither(second:)#Building-keyframe-track-content)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
``static func buildBlock() -> some KeyframeTrackContent<Value>
`[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframetrackcontentbuilder/buildeither(first:))[`static func buildExpression<K>(K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildexpression(_:))`static func buildPartialBlock(accumulated: some KeyframeTrackContent<Value>, next: some KeyframeTrackContent<Value>) -> some KeyframeTrackContent<Value>
`[`static func buildPartialBlock<K>(first: K) -> K`](/documentation/swiftui/keyframetrackcontentbuilder/buildpartialblock(first:))[`struct Conditional`](/documentation/swiftui/keyframetrackcontentbuilder/conditional)A conditional result from the result builder.