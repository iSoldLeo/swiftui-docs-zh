--- 来源：https://developer.apple.com/documentation/SwiftUI/TabContentBuilder/buildEither(second:)

抓取时间：2025-12-03T06:01:21Z

---

# buildEither(second:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- [ buildEither(second:) ](/documentation/SwiftUI/TabContentBuilder/buildEither(second:))

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- buildEither(second:) 

类型 方法# buildEither(second:)

iOS 18.0+、iPadOS 18.0+、Mac Catalyst 18.0+、macOS 15.0+、tvOS 18.0+、vSOS 2.0+、watchOS 11.0+

```
static func buildEither<T, F>(second: F) -> _ConditionalContent<T, F> where TabValue == T.TabValue, T : TabContent, F : TabContent, T.TabValue == F.TabValue
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContentBuilder/buildEither(second:)
crawled: 2025-12-03T06:01:21Z
---

# buildEither(second:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- [ buildEither(second:) ](/documentation/SwiftUI/TabContentBuilder/buildEither(second:))

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

-  buildEither(second:) 

Type Method# buildEither(second:)

iOS 18.0+iPadOS 18.0+Mac Catalyst 18.0+macOS 15.0+tvOS 18.0+visionOS 2.0+watchOS 11.0+

```
static func buildEither<T, F>(second: F) -> _ConditionalContent<T, F> where TabValue == T.TabValue, T : TabContent, F : TabContent, T.TabValue == F.TabValue
```

