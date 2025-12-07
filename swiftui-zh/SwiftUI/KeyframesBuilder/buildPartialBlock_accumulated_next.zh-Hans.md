---
来源：https://developer.apple.com/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(累计：next:)
抓取时间：2025-12-03T06:14:07Z
---

# buildPartialBlock(accumulated:next:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- [ buildPartialBlock(accumulated:next:) ](/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(accumulated:next:))

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- buildPartialBlock(accumulated:next:)

类型 方法# buildPartialBlock(accumulated:next:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildPartialBlock(
    accumulated: some KeyframeTrackContent<Value>,
    next: some KeyframeTrackContent<Value>
) -> some KeyframeTrackContent<Value>

```

 显示所有声明 ## [See Also](/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(accumulated:next:)#see-also)

### [构建关键帧](/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(accumulated:next:)#Building-keyframes)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildFinalResult(_:)`](/documentation/swiftui/keyframesbuilder/buildfinalresult(_:))[`static buildPartialBlock(first:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))

---
source: https://developer.apple.com/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(accumulated:next:)
crawled: 2025-12-03T06:14:07Z
---

# buildPartialBlock(accumulated:next:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

- [ buildPartialBlock(accumulated:next:) ](/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(accumulated:next:))

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

-  buildPartialBlock(accumulated:next:) 

Type Method# buildPartialBlock(accumulated:next:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildPartialBlock(
    accumulated: some KeyframeTrackContent<Value>,
    next: some KeyframeTrackContent<Value>
) -> some KeyframeTrackContent<Value>

```

 Show all declarations ## [See Also](/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(accumulated:next:)#see-also)

### [Building keyframes](/documentation/SwiftUI/KeyframesBuilder/buildPartialBlock(accumulated:next:)#Building-keyframes)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildFinalResult(_:)`](/documentation/swiftui/keyframesbuilder/buildfinalresult(_:))[`static buildPartialBlock(first:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))