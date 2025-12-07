---
来源：https://developer.apple.com/documentation/swiftui/keyframesbuilder/buildpartialblock(first:)
抓取时间： 2025-12-04T13:15:19Z
---

# 构建部分代码块（first:） | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- [ buildPartialBlock(first:) ](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- buildPartialBlock(first:)

类型 方法# buildPartialBlock(first:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildPartialBlock<Content>(first: Content) -> Content where Value == Content.Value, Content : Keyframes
```

 显示所有声明 ## [See Also](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:)#see-also)

### [构建关键帧](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:)#Building-keyframes)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildFinalResult(_:)`](/documentation/swiftui/keyframesbuilder/buildfinalresult(_:))[`static buildPartialBlock(accumulated:next:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(accumulated:next:))

---
source: https://developer.apple.com/documentation/swiftui/keyframesbuilder/buildpartialblock(first:)
crawled: 2025-12-04T13:15:19Z
---

# buildPartialBlock(first:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

- [ buildPartialBlock(first:) ](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

-  buildPartialBlock(first:) 

Type Method# buildPartialBlock(first:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildPartialBlock<Content>(first: Content) -> Content where Value == Content.Value, Content : Keyframes
```

 Show all declarations ## [See Also](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:)#see-also)

### [Building keyframes](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:)#Building-keyframes)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildFinalResult(_:)`](/documentation/swiftui/keyframesbuilder/buildfinalresult(_:))[`static buildPartialBlock(accumulated:next:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(accumulated:next:))