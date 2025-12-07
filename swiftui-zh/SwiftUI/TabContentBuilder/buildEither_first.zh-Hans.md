--- 来源：https://developer.apple.com/documentation/SwiftUI/TabContentBuilder/buildEither(first:)

抓取时间：2025-12-01T10:50:11Z

---

# buildEither(first:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- [ buildEither(first:) ](/documentation/SwiftUI/TabContentBuilder/buildEither(first:))

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- buildEither(first:) 

类型 方法# buildEither(first:)

iOS 18.0+、iPadOS 18.0+、Mac Catalyst 18.0+、macOS 15.0+、tvOS 18.0+、vSOS 2.0+、watchOS 11.0+

```
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where TabValue == T.TabValue, T : TabContent, F : TabContent, T.TabValue == F.TabValue
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContentBuilder/buildEither(first:)
crawled: 2025-12-01T10:50:11Z
---

# buildEither(first:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- [ buildEither(first:) ](/documentation/SwiftUI/TabContentBuilder/buildEither(first:))

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

-  buildEither(first:) 

Type Method# buildEither(first:)

iOS 18.0+iPadOS 18.0+Mac Catalyst 18.0+macOS 15.0+tvOS 18.0+visionOS 2.0+watchOS 11.0+

```
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where TabValue == T.TabValue, T : TabContent, F : TabContent, T.TabValue == F.TabValue
```

