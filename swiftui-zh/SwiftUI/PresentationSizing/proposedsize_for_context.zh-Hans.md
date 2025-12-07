--- 来源：https://developer.apple.com/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:)

抓取时间：2025-12-03T06:02:22Z

---

# proposedSize(for:context:) | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ PresentationSizing ](/documentation/swiftui/presentationsizing)

- [ proposedSize(for:context:) ](/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:))

- [ PresentationSizing ](/documentation/swiftui/presentationsizing)

- proposedSize(for:context:) 

实例方法# proposedSize(for:context:)

iOS 18.0+、iPadOS 18.0+、Mac Catalyst 18.0+、macOS 15.0+、tvOS 18.0+、vVOS 2.0+、watchOS 11.0+

```
func proposedSize(
    for root: PresentationSizingRoot,
    context: PresentationSizingContext
) -> ProposedViewSize
```

**Required**

## [参见另请参阅](/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:)#see-also)

### [创建自定义演示尺寸](/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:)#Creating-custom-presentation-size)

[`func fitted(horizontal: Bool, vertical: Bool) -> some PresentationSizing`](/documentation/swiftui/presentationsizing/fitted(horizontal:vertical:))[`func sticky(horizontal: Bool, vertical: Bool) -> some PresentationSizing`](/documentation/swiftui/presentationsizing/sticky(horizontal:vertical:))修改自身，使其在指定尺寸内保持粘性——不断增大，但不会缩小。

---
source: https://developer.apple.com/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:)
crawled: 2025-12-03T06:02:22Z
---

# proposedSize(for:context:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ PresentationSizing ](/documentation/swiftui/presentationsizing)

- [ proposedSize(for:context:) ](/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:))

- [ PresentationSizing ](/documentation/swiftui/presentationsizing)

-  proposedSize(for:context:) 

Instance Method# proposedSize(for:context:)

iOS 18.0+iPadOS 18.0+Mac Catalyst 18.0+macOS 15.0+tvOS 18.0+visionOS 2.0+watchOS 11.0+

```
func proposedSize(
    for root: PresentationSizingRoot,
    context: PresentationSizingContext
) -> ProposedViewSize
```

**Required**

## [See Also](/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:)#see-also)

### [Creating custom presentation size](/documentation/SwiftUI/PresentationSizing/proposedSize(for:context:)#Creating-custom-presentation-size)

[`func fitted(horizontal: Bool, vertical: Bool) -> some PresentationSizing`](/documentation/swiftui/presentationsizing/fitted(horizontal:vertical:))[`func sticky(horizontal: Bool, vertical: Bool) -> some PresentationSizing`](/documentation/swiftui/presentationsizing/sticky(horizontal:vertical:))Modifies self to be sticky in the specified dimensions — growing, but not shrinking.