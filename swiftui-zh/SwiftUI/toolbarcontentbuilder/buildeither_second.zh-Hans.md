---
来源：https://developer.apple.com/documentation/SwiftUI/ToolbarContentBuilder/buildEither(Second:)
抓取时间：2025-12-03T06:04:42Z
---

# buildEither(second:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 工具栏内容生成器 ](/documentation/swiftui/toolbarcontentbuilder)

- [ buildEither(second:) ](/documentation/SwiftUI/ToolbarContentBuilder/buildEither(second:))

- [ 工具栏内容生成器 ](/documentation/swiftui/toolbarcontentbuilder)

- buildEither(second:)

类型 方法# buildEither(second:)

iOS 16.0+iPadOS 16.0+Mac Catalyst 16.0+macOS 13.0+tvOS 16.0+visionOS 1.0+watchOS 9.0+

```
static func buildEither<TrueContent, FalseContent>(second: FalseContent) -> _ConditionalContent<TrueContent, FalseContent> where TrueContent : CustomizableToolbarContent, FalseContent : CustomizableToolbarContent
```

 显示所有声明 ## [See Also](/documentation/SwiftUI/ToolbarContentBuilder/buildEither(second:)#see-also)

### [构建有条件的工具栏内容](/documentation/SwiftUI/ToolbarContentBuilder/buildEither(second:)#构建有条件的工具栏内容)

[`static buildIf(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildif(_:))[`static buildEither(first:)`](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:))[`static buildExpression(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildexpression(_:)) 在构建器中构建表达式。[`static buildLimitedAvailability(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildlimitedavailability(_:))

---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarContentBuilder/buildEither(second:)
crawled: 2025-12-03T06:04:42Z
---

# buildEither(second:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ToolbarContentBuilder ](/documentation/swiftui/toolbarcontentbuilder)

- [ buildEither(second:) ](/documentation/SwiftUI/ToolbarContentBuilder/buildEither(second:))

- [ ToolbarContentBuilder ](/documentation/swiftui/toolbarcontentbuilder)

-  buildEither(second:) 

Type Method# buildEither(second:)

iOS 16.0+iPadOS 16.0+Mac Catalyst 16.0+macOS 13.0+tvOS 16.0+visionOS 1.0+watchOS 9.0+

```
static func buildEither<TrueContent, FalseContent>(second: FalseContent) -> _ConditionalContent<TrueContent, FalseContent> where TrueContent : CustomizableToolbarContent, FalseContent : CustomizableToolbarContent
```

 Show all declarations ## [See Also](/documentation/SwiftUI/ToolbarContentBuilder/buildEither(second:)#see-also)

### [Building conditional toolbar content](/documentation/SwiftUI/ToolbarContentBuilder/buildEither(second:)#Building-conditional-toolbar-content)

[`static buildIf(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildif(_:))[`static buildEither(first:)`](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:))[`static buildExpression(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildexpression(_:))Builds an expression within the builder.[`static buildLimitedAvailability(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildlimitedavailability(_:))