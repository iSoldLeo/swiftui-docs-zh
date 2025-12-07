---
来源： https://developer.apple.com/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:)
抓取时间： 2025-12-04T13:40:38Z
---

# buildBlock(_:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ AccessibilityRotorContentBuilder ](/documentation/swiftui/accessibilityrotorcontentbuilder)

- [ buildBlock(_:) ](/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:))

- [ 无障碍内容生成器 ](/documentation/swiftui/accessibilityrotorcontentbuilder)

- buildBlock(_:)

类型 方法# buildBlock(_:)

iOS 15.0+iPadOS 15.0+Mac Catalyst 15.0+macOS 12.0+tvOS 15.0+visionOS 1.0+watchOS 8.0+

```
static func buildBlock<Content>(_ content: Content) -> some AccessibilityRotorContent where Content : AccessibilityRotorContent

```

 显示所有声明 ## [See Also](/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:)#see-also)

### [构建导航内容](/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:)#Building-navigation-content)

[`static func buildIf<Content>(Content?) -> some AccessibilityRotorContent`](/documentation/swiftui/accessibilityrotorcontentbuilder/buildif(_:))[`static func buildExpression<Content>(Content) -> Content`](/documentation/swiftui/accessibilityrotorcontentbuilder/buildexpression(_:))在构建器中构建表达式。

---
source: https://developer.apple.com/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:)
crawled: 2025-12-04T13:40:38Z
---

# buildBlock(_:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ AccessibilityRotorContentBuilder ](/documentation/swiftui/accessibilityrotorcontentbuilder)

- [ buildBlock(_:) ](/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:))

- [ AccessibilityRotorContentBuilder ](/documentation/swiftui/accessibilityrotorcontentbuilder)

-  buildBlock(_:) 

Type Method# buildBlock(_:)

iOS 15.0+iPadOS 15.0+Mac Catalyst 15.0+macOS 12.0+tvOS 15.0+visionOS 1.0+watchOS 8.0+

```
static func buildBlock<Content>(_ content: Content) -> some AccessibilityRotorContent where Content : AccessibilityRotorContent

```

 Show all declarations ## [See Also](/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:)#see-also)

### [Building navigation content](/documentation/swiftui/accessibilityrotorcontentbuilder/buildblock(_:)#Building-navigation-content)

[`static func buildIf<Content>(Content?) -> some AccessibilityRotorContent`](/documentation/swiftui/accessibilityrotorcontentbuilder/buildif(_:))[`static func buildExpression<Content>(Content) -> Content`](/documentation/swiftui/accessibilityrotorcontentbuilder/buildexpression(_:))Builds an expression within the builder.