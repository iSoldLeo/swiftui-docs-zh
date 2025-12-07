--- 来源：https://developer.apple.com/documentation/SwiftUI/TabContentBuilder/buildBlock(_:_:_:_:_:_:)

抓取时间：2025-12-03T06:00:43Z

---

# buildBlock(_:_:_:_:_:_:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- [ buildBlock(_:_:_:_:_:_:) ](/documentation/SwiftUI/TabContentBuilder/buildBlock(_:_:_:_:_:_:))

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- buildBlock(_:_:_:_:_:_:) 

类型 方法# buildBlock(_:_:_:_:_:_:_:)

iOS 18.0+、iPadOS 18.0+、Mac Catalyst 18.0+、macOS 15.0+、tvOS 18.0+、vvOS 2.0+、watchOS 11.0+

```
static func buildBlock<C0, C1, C2, C3, C4, C5>(
    _ c0: C0,
    _ c1: C1,
    _ c2: C2,
    _ c3: C3,
    _ c4: C4,
    _ c5: C5
) -> some TabContent<TabValue> where TabValue == C0.TabValue, C0 : TabContent, C1 : TabContent, C2 : TabContent, C3 : TabContent, C4 : TabContent, C5 : TabContent, C0.TabValue == C1.TabValue, C1.TabValue == C2.TabValue, C2.TabValue == C3.TabValue, C3.TabValue == C4.TabValue, C4.TabValue == C5.TabValue

```

可用版本`TabValue` 符合 `Hashable`。

---
source: https://developer.apple.com/documentation/SwiftUI/TabContentBuilder/buildBlock(_:_:_:_:_:_:)
crawled: 2025-12-03T06:00:43Z
---

# buildBlock(_:_:_:_:_:_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

- [ buildBlock(_:_:_:_:_:_:) ](/documentation/SwiftUI/TabContentBuilder/buildBlock(_:_:_:_:_:_:))

- [ TabContentBuilder ](/documentation/swiftui/tabcontentbuilder)

-  buildBlock(_:_:_:_:_:_:) 

Type Method# buildBlock(_:_:_:_:_:_:)

iOS 18.0+iPadOS 18.0+Mac Catalyst 18.0+macOS 15.0+tvOS 18.0+visionOS 2.0+watchOS 11.0+

```
static func buildBlock<C0, C1, C2, C3, C4, C5>(
    _ c0: C0,
    _ c1: C1,
    _ c2: C2,
    _ c3: C3,
    _ c4: C4,
    _ c5: C5
) -> some TabContent<TabValue> where TabValue == C0.TabValue, C0 : TabContent, C1 : TabContent, C2 : TabContent, C3 : TabContent, C4 : TabContent, C5 : TabContent, C0.TabValue == C1.TabValue, C1.TabValue == C2.TabValue, C2.TabValue == C3.TabValue, C3.TabValue == C4.TabValue, C4.TabValue == C5.TabValue

```

Available when `TabValue` conforms to `Hashable`.