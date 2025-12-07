---
来源：https://developer.apple.com/documentation/swiftui/keyframesbuilder/buildeither(Second:)
抓取时间：2025-12-04T13:15:00Z
---

# buildEither(second:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- [ buildEither(second:) ](/documentation/swiftui/keyframesbuilder/buildeither(second:))

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- buildEither(second:)

类型 方法# buildEither(second:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildEither<First, Second>(second component: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second> where Value == First.Value, First : KeyframeTrackContent, Second : KeyframeTrackContent, First.Value == Second.Value
```

## [See Also](/documentation/swiftui/keyframesbuilder/buildeither(second:)#see-also)

### [构建关键帧](/documentation/swiftui/keyframesbuilder/buildeither(second:)#构建关键帧)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildFinalResult(_:)`](/documentation/swiftui/keyframesbuilder/buildfinalresult(_:))[`static buildPartialBlock(accumulated:next:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(accumulated:next:))[`static buildPartialBlock(first:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))

---
source: https://developer.apple.com/documentation/swiftui/keyframesbuilder/buildeither(second:)
crawled: 2025-12-04T13:15:00Z
---

# buildEither(second:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

- [ buildEither(second:) ](/documentation/swiftui/keyframesbuilder/buildeither(second:))

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

-  buildEither(second:) 

Type Method# buildEither(second:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildEither<First, Second>(second component: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second> where Value == First.Value, First : KeyframeTrackContent, Second : KeyframeTrackContent, First.Value == Second.Value
```

## [See Also](/documentation/swiftui/keyframesbuilder/buildeither(second:)#see-also)

### [Building keyframes](/documentation/swiftui/keyframesbuilder/buildeither(second:)#Building-keyframes)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildFinalResult(_:)`](/documentation/swiftui/keyframesbuilder/buildfinalresult(_:))[`static buildPartialBlock(accumulated:next:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(accumulated:next:))[`static buildPartialBlock(first:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))