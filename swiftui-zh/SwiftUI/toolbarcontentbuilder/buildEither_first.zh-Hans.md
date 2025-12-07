---
来源：https://developer.apple.com/documentation/swiftui/toolbarcontentbuilder/buildeither(first:)
抓取时间： 2025-12-04T13:09:52Z
---

# buildEither(first:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 工具栏内容生成器 ](/documentation/swiftui/toolbarcontentbuilder)

- [ buildEither(first:) ](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:))

- [ 工具栏内容生成器 ](/documentation/swiftui/toolbarcontentbuilder)

- buildEither(first:)

类型 方法# buildEither(first:)

iOS 16.0+iPadOS 16.0+Mac Catalyst 16.0+macOS 13.0+tvOS 16.0+visionOS 1.0+watchOS 9.0+

```
static func buildEither<TrueContent, FalseContent>(first: TrueContent) -> _ConditionalContent<TrueContent, FalseContent> where TrueContent : CustomizableToolbarContent, FalseContent : CustomizableToolbarContent
```

 显示所有声明 ## [See Also](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:)#see-also)

### [构建有条件的工具栏内容](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:)#构建有条件的工具栏内容)

[`static buildIf(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildif(_:))[`static buildEither(second:)`](/documentation/swiftui/toolbarcontentbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildexpression(_:)) 在构建器中构建表达式。[`static buildLimitedAvailability(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildlimitedavailability(_:))

---
source: https://developer.apple.com/documentation/swiftui/toolbarcontentbuilder/buildeither(first:)
crawled: 2025-12-04T13:09:52Z
---

# buildEither(first:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ToolbarContentBuilder ](/documentation/swiftui/toolbarcontentbuilder)

- [ buildEither(first:) ](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:))

- [ ToolbarContentBuilder ](/documentation/swiftui/toolbarcontentbuilder)

-  buildEither(first:) 

Type Method# buildEither(first:)

iOS 16.0+iPadOS 16.0+Mac Catalyst 16.0+macOS 13.0+tvOS 16.0+visionOS 1.0+watchOS 9.0+

```
static func buildEither<TrueContent, FalseContent>(first: TrueContent) -> _ConditionalContent<TrueContent, FalseContent> where TrueContent : CustomizableToolbarContent, FalseContent : CustomizableToolbarContent
```

 Show all declarations ## [See Also](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:)#see-also)

### [Building conditional toolbar content](/documentation/swiftui/toolbarcontentbuilder/buildeither(first:)#Building-conditional-toolbar-content)

[`static buildIf(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildif(_:))[`static buildEither(second:)`](/documentation/swiftui/toolbarcontentbuilder/buildeither(second:))[`static buildExpression(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildexpression(_:))Builds an expression within the builder.[`static buildLimitedAvailability(_:)`](/documentation/swiftui/toolbarcontentbuilder/buildlimitedavailability(_:))