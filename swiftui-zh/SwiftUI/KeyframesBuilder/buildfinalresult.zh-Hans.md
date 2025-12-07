---
来源： https://developer.apple.com/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:)
抓取时间： 2025-12-01T11:03:09Z
---

# buildFinalResult(_:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- [ buildFinalResult(_:) ](/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:))

- [ 关键帧生成器 ](/documentation/swiftui/keyframesbuilder)

- buildFinalResult(_:)

类型 方法# buildFinalResult(_:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildFinalResult<Content>(_ component: Content) -> Content where Value == Content.Value, Content : Keyframes
```

 显示所有声明 ## [See Also](/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:)#see-also)

### [构建关键帧](/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:)#Building-keyframes)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildPartialBlock(accumulated:next:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(accumulated:next:))[`static buildPartialBlock(first:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))

---
source: https://developer.apple.com/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:)
crawled: 2025-12-01T11:03:09Z
---

# buildFinalResult(_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

- [ buildFinalResult(_:) ](/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:))

- [ KeyframesBuilder ](/documentation/swiftui/keyframesbuilder)

-  buildFinalResult(_:) 

Type Method# buildFinalResult(_:)

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+watchOS 10.0+

```
static func buildFinalResult<Content>(_ component: Content) -> Content where Value == Content.Value, Content : Keyframes
```

 Show all declarations ## [See Also](/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:)#see-also)

### [Building keyframes](/documentation/SwiftUI/KeyframesBuilder/buildFinalResult(_:)#Building-keyframes)

`static func buildArray([some KeyframeTrackContent<Value>]) -> some KeyframeTrackContent<Value>
`[`static buildBlock()`](/documentation/swiftui/keyframesbuilder/buildblock())[`static func buildEither<First, Second>(first: First) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(first:))[`static func buildEither<First, Second>(second: Second) -> KeyframeTrackContentBuilder<Value>.Conditional<Value, First, Second>`](/documentation/swiftui/keyframesbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/keyframesbuilder/buildexpression(_:))Keyframes[`static buildPartialBlock(accumulated:next:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(accumulated:next:))[`static buildPartialBlock(first:)`](/documentation/swiftui/keyframesbuilder/buildpartialblock(first:))