--- 来源：https://developer.apple.com/documentation/SwiftUI/ContentToolbarPlacement
抓取时间：2025-12-02T17:31:21Z

---

# ContentToolbarPlacement | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 内容工具栏位置 ](/documentation/SwiftUI/ContentToolbarPlacement)

- 内容工具栏位置

结构# 内容工具栏位置

iOS 18.4+、iPadOS 18.4+、Mac Catalyst 18.4+、macOS 15.4+、tvOS 18.4+、visionOS 2.4+、watchOS 11.4+

```
struct ContentToolbarPlacement
```

## [主题](/documentation/SwiftUI/ContentToolbarPlacement#topics)

### [类型属性](/documentation/SwiftUI/ContentToolbarPlacement#Type-Properties)

[`static let tabViewSidebar: ContentToolbarPlacement`](/documentation/swiftui/contenttoolbarplacement/tabviewsidebar)标签视图侧边栏。在某些平台上使用 `.sidebarAdaptable` 标签视图样式时，会出现此功能。## [关联关系](/documentation/SwiftUI/ContentToolbarPlacement#relationships)

### [符合](/documentation/SwiftUI/ContentToolbarPlacement#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Hashable`](/documentation/Swift/Hashable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [另请参阅](/documentation/SwiftUI/ContentToolbarPlacement#see-also)

### [设置工具栏]可见性](/documentation/SwiftUI/ContentToolbarPlacement#Setting-toolbar-visibility)

[`func toolbar(Visibility, for: ToolbarPlacement...) -> some View`](/documentation/swiftui/view/toolbar(_:for:))指定由 SwiftUI 管理的工具栏的可见性。[`func toolbarVisibility(Visibility, for: ToolbarPlacement...) -> some View`](/documentation/swiftui/view/toolbarvisibility(_:for:))指定由 SwiftUI 管理的工具栏的可见性。[`func toolbarBackgroundVisibility(Visibility, for: ToolbarPlacement...) -> some View`](/documentation/swiftui/view/toolbarbackgroundvisibility(_:for:))指定由 SwiftUI 管理的工具栏上背景的首选可见性。[`struct ToolbarPlacement`](/documentation/swiftui/toolbarplacement)工具栏的位置。

---
source: https://developer.apple.com/documentation/SwiftUI/ContentToolbarPlacement
crawled: 2025-12-02T17:31:21Z
---

# ContentToolbarPlacement | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ ContentToolbarPlacement ](/documentation/SwiftUI/ContentToolbarPlacement)

-  ContentToolbarPlacement 

Structure# ContentToolbarPlacement

iOS 18.4+iPadOS 18.4+Mac Catalyst 18.4+macOS 15.4+tvOS 18.4+visionOS 2.4+watchOS 11.4+

```
struct ContentToolbarPlacement
```

## [Topics](/documentation/SwiftUI/ContentToolbarPlacement#topics)

### [Type Properties](/documentation/SwiftUI/ContentToolbarPlacement#Type-Properties)

[`static let tabViewSidebar: ContentToolbarPlacement`](/documentation/swiftui/contenttoolbarplacement/tabviewsidebar)The tab view sidebar. This is present on certain platforms when using the `.sidebarAdaptable` tab view style.## [Relationships](/documentation/SwiftUI/ContentToolbarPlacement#relationships)

### [Conforms To](/documentation/SwiftUI/ContentToolbarPlacement#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Hashable`](/documentation/Swift/Hashable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [See Also](/documentation/SwiftUI/ContentToolbarPlacement#see-also)

### [Setting toolbar visibility](/documentation/SwiftUI/ContentToolbarPlacement#Setting-toolbar-visibility)

[`func toolbar(Visibility, for: ToolbarPlacement...) -> some View`](/documentation/swiftui/view/toolbar(_:for:))Specifies the visibility of a bar managed by SwiftUI.[`func toolbarVisibility(Visibility, for: ToolbarPlacement...) -> some View`](/documentation/swiftui/view/toolbarvisibility(_:for:))Specifies the visibility of a bar managed by SwiftUI.[`func toolbarBackgroundVisibility(Visibility, for: ToolbarPlacement...) -> some View`](/documentation/swiftui/view/toolbarbackgroundvisibility(_:for:))Specifies the preferred visibility of backgrounds on a bar managed by SwiftUI.[`struct ToolbarPlacement`](/documentation/swiftui/toolbarplacement)The placement of a toolbar.