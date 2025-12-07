---
来源： https://developer.apple.com/documentation/SwiftUI/Image/DynamicRange
抓取时间： 2025-12-03T04:29:14Z
---

# Image.DynamicRange | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ Image ](/documentation/swiftui/image)

- [ Image.DynamicRange ](/documentation/SwiftUI/Image/DynamicRange)

- [ 图像 ](/documentation/swiftui/image)

- 图像动态范围

结构# Image.DynamicRange

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+

```
struct DynamicRange
```

## [主题](/documentation/SwiftUI/Image/DynamicRange#topics)

### [获取动态范围值](/documentation/SwiftUI/Image/DynamicRange#Getting-dynamic-range-values)

[`static let standard: Image.DynamicRange`](/documentation/swiftui/image/dynamicrange/standard)将图像内容动态范围限制在标准范围内。[`static let high: Image.DynamicRange`](/documentation/swiftui/image/dynamicrange/high)允许图像内容使用不受限制的扩展范围。 [`static let constrainedHigh: Image.DynamicRange`](/documentation/swiftui/image/dynamicrange/constrainedhigh)允许图像内容使用某些扩展范围。这适合将 HDR 内容放在 SDR 内容旁边。## [关系](/documentation/SwiftUI/Image/DynamicRange#relationships)

### [符合](/documentation/SwiftUI/Image/DynamicRange#conforms-to)

- [⟦ic_0007⟧](⟦lu_0018⟧)

- [⟦ic_0006⟧](⟦lu_0017⟧)

- [⟦ic_0005⟧](⟦lu_0016⟧)

- [⟦ic_0004⟧](⟦lu_0015⟧)

## [See Also](/documentation/SwiftUI/Image/DynamicRange#see-also)

### [指定动态范围](/documentation/SwiftUI/Image/DynamicRange#Specifying-dynamic-range)

[`func allowedDynamicRange(Image.DynamicRange?) -> Image`](/documentation/swiftui/image/alloweddynamicrange(_:)返回以指定的允许动态范围配置的新图像。

---
source: https://developer.apple.com/documentation/SwiftUI/Image/DynamicRange
crawled: 2025-12-03T04:29:14Z
---

# Image.DynamicRange | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ Image ](/documentation/swiftui/image)

- [ Image.DynamicRange ](/documentation/SwiftUI/Image/DynamicRange)

- [ Image ](/documentation/swiftui/image)

-  Image.DynamicRange 

Structure# Image.DynamicRange

iOS 17.0+iPadOS 17.0+Mac Catalyst 17.0+macOS 14.0+tvOS 17.0+visionOS 1.0+

```
struct DynamicRange
```

## [Topics](/documentation/SwiftUI/Image/DynamicRange#topics)

### [Getting dynamic range values](/documentation/SwiftUI/Image/DynamicRange#Getting-dynamic-range-values)

[`static let standard: Image.DynamicRange`](/documentation/swiftui/image/dynamicrange/standard)Restrict the image content dynamic range to the standard range.[`static let high: Image.DynamicRange`](/documentation/swiftui/image/dynamicrange/high)Allow image content to use an unrestricted extended range.[`static let constrainedHigh: Image.DynamicRange`](/documentation/swiftui/image/dynamicrange/constrainedhigh)Allow image content to use some extended range. This is appropriate for placing HDR content next to SDR content.## [Relationships](/documentation/SwiftUI/Image/DynamicRange#relationships)

### [Conforms To](/documentation/SwiftUI/Image/DynamicRange#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Hashable`](/documentation/Swift/Hashable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [See Also](/documentation/SwiftUI/Image/DynamicRange#see-also)

### [Specifying dynamic range](/documentation/SwiftUI/Image/DynamicRange#Specifying-dynamic-range)

[`func allowedDynamicRange(Image.DynamicRange?) -> Image`](/documentation/swiftui/image/alloweddynamicrange(_:))Returns a new image configured with the specified allowed dynamic range.[`var allowedDynamicRange: Image.DynamicRange?`](/documentation/swiftui/environmentvalues/alloweddynamicrange)The allowed dynamic range for the view, or nil.