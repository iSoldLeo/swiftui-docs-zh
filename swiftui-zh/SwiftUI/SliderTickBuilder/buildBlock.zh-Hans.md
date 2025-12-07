---
来源：https://developer.apple.com/documentation/SwiftUI/SliderTickBuilder/buildBlock(_:_:_:_:_:_:_:_:_:_:_:_:_:_:_::)
抓取时间：2025-12-03T20:27:10Z
---

# buildBlock(_:_:_:_:_:_:_:_:_:_:_:_:_:_:_:_:_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ SliderTickBuilder ](/documentation/swiftui/slidertickbuilder)

- [ buildBlock(_:_:_:_:_:_:_:_:_:_:_:_:_:_:_:) ](/documentation/SwiftUI/SliderTickBuilder/buildBlock(_:_:_:_:_:_:_:_:_:_:))

- [ 滑块标签生成器 ](/documentation/swiftui/slidertickbuilder)

- buildBlock(_:_:_:_:_:_:_:_:_:_:)

类型 方法# buildBlock(_:_:_:_:_:_:_:_:_:_:_:_:_:_:_:)

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+visionOS 26.0+watchOS 26.0+

```
static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8, C9>(
    _ c0: C0,
    _ c1: C1,
    _ c2: C2,
    _ c3: C3,
    _ c4: C4,
    _ c5: C5,
    _ c6: C6,
    _ c7: C7,
    _ c8: C8,
    _ c9: C9
) -> some SliderTickContent<V> where V == C0.Value, C0 : SliderTickContent, C1 : SliderTickContent, C2 : SliderTickContent, C3 : SliderTickContent, C4 : SliderTickContent, C5 : SliderTickContent, C6 : SliderTickContent, C7 : SliderTickContent, C8 : SliderTickContent, C9 : SliderTickContent, C0.Value == C1.Value, C1.Value == C2.Value, C2.Value == C3.Value, C3.Value == C4.Value, C4.Value == C5.Value, C5.Value == C6.Value, C6.Value == C7.Value, C7.Value == C8.Value, C8.Value == C9.Value

```

当 `V` 符合 `BinaryFloatingPoint` 时可用。

---
source: https://developer.apple.com/documentation/SwiftUI/SliderTickBuilder/buildBlock(_:_:_:_:_:_:_:_:_:_:)
crawled: 2025-12-03T20:27:10Z
---

# buildBlock(_:_:_:_:_:_:_:_:_:_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ SliderTickBuilder ](/documentation/swiftui/slidertickbuilder)

- [ buildBlock(_:_:_:_:_:_:_:_:_:_:) ](/documentation/SwiftUI/SliderTickBuilder/buildBlock(_:_:_:_:_:_:_:_:_:_:))

- [ SliderTickBuilder ](/documentation/swiftui/slidertickbuilder)

-  buildBlock(_:_:_:_:_:_:_:_:_:_:) 

Type Method# buildBlock(_:_:_:_:_:_:_:_:_:_:)

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+visionOS 26.0+watchOS 26.0+

```
static func buildBlock<C0, C1, C2, C3, C4, C5, C6, C7, C8, C9>(
    _ c0: C0,
    _ c1: C1,
    _ c2: C2,
    _ c3: C3,
    _ c4: C4,
    _ c5: C5,
    _ c6: C6,
    _ c7: C7,
    _ c8: C8,
    _ c9: C9
) -> some SliderTickContent<V> where V == C0.Value, C0 : SliderTickContent, C1 : SliderTickContent, C2 : SliderTickContent, C3 : SliderTickContent, C4 : SliderTickContent, C5 : SliderTickContent, C6 : SliderTickContent, C7 : SliderTickContent, C8 : SliderTickContent, C9 : SliderTickContent, C0.Value == C1.Value, C1.Value == C2.Value, C2.Value == C3.Value, C3.Value == C4.Value, C4.Value == C5.Value, C5.Value == C6.Value, C6.Value == C7.Value, C7.Value == C8.Value, C8.Value == C9.Value

```

Available when `V` conforms to `BinaryFloatingPoint`.