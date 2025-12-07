---
来源： https://developer.apple.com/documentation/SwiftUI/TabBarMinimizeBehavior
抓取时间： 2025-12-02T17:29:53Z
---

# TabBarMinimizeBehavior | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ TabBarMinimizeBehavior ](/documentation/SwiftUI/TabBarMinimizeBehavior)

- TabBarMinimizeBehavior

Structure# TabBarMinimizeBehavior

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+tvOS 26.0+visionOS 26.0+watchOS 26.0+

```
struct TabBarMinimizeBehavior
```

## [主题](/documentation/SwiftUI/TabBarMinimizeBehavior#topics)

### [类型属性](/documentation/SwiftUI/TabBarMinimizeBehavior#Type-Properties)

[`static let automatic: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/automatic)根据周围环境自动确定行为。[`static let never: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/never)从不最小化标签栏。 [`static let onScrollDown: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/onscrolldown)向下滚动开始时最小化标签栏。仅 iPhone 支持将标签栏最小化。[`static let onScrollUp: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/onscrollup)向上滚动时将标签栏最小化。仅 iPhone 支持将标签栏最小化。## [关系](/documentation/SwiftUI/TabBarMinimizeBehavior#relationships)

### [符合](/documentation/SwiftUI/TabBarMinimizeBehavior#conforms-to)

- [⟦ic_0014⟧](⟦lu_0033⟧)

- [⟦ic_0013⟧](⟦lu_0032⟧)

- [⟦ic_0012⟧](⟦lu_0031⟧)

- [⟦ic_0011⟧](⟦lu_0030⟧)

## [See Also](/documentation/SwiftUI/TabBarMinimizeBehavior#see-also)

### [配置标签栏](/documentation/SwiftUI/TabBarMinimizeBehavior#Configuring-a-tab-bar)

[`func defaultAdaptableTabBarPlacement(AdaptableTabBarPlacement) -> some View`](/documentation/swiftui/view/defaultadaptabletabbarplacement(_:)使用自适应侧边栏样式指定选项卡视图中选项卡的默认位置[`func tabViewSidebarHeader<Content>(content: () -> Content) -> some View`](/documentation/swiftui/view/tabviewsidebarheader(content:))为选项卡视图的侧边栏添加自定义页眉。[`func tabViewSidebarFooter<Content>(content: () -> Content) -> some View`](/documentation/swiftui/view/tabviewsidebarfooter(content:))Adds a custom footer to the sidebar of a tab view.[`func tabViewSidebarBottomBar<Content>(content: () -> Content) -> some View`](/documentation/swiftui/view/tabviewsidebarbottombar(content:))为标签视图的侧边栏添加自定义页脚。[`struct AdaptableTabBarPlacement`](/documentation/swiftui/adaptabletabbarplacement)在选项卡视图中使用自适应侧边栏样式放置选项卡。[`var tabBarPlacement: TabBarPlacement?`](/documentation/swiftui/environmentvalues/tabbarplacement)标签栏的当前位置。 [`struct TabBarPlacement`](/documentation/swiftui/tabbarplacement)标签视图中标签的位置。[`var isTabBarShowingSections: Bool`](/documentation/swiftui/environmentvalues/istabbarshowingsections)一个布尔值，用于确定选项卡视图是否显示选项卡部分的展开内容。 [`enum TabViewBottomAccessoryPlacement`](/documentation/swiftui/tabviewbottomaccessoryplacement)选项卡视图中底部附件的位置。您可以用它根据位置调整附件视图的内容。

---
source: https://developer.apple.com/documentation/SwiftUI/TabBarMinimizeBehavior
crawled: 2025-12-02T17:29:53Z
---

# TabBarMinimizeBehavior | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ TabBarMinimizeBehavior ](/documentation/SwiftUI/TabBarMinimizeBehavior)

-  TabBarMinimizeBehavior 

Structure# TabBarMinimizeBehavior

iOS 26.0+iPadOS 26.0+Mac Catalyst 26.0+macOS 26.0+tvOS 26.0+visionOS 26.0+watchOS 26.0+

```
struct TabBarMinimizeBehavior
```

## [Topics](/documentation/SwiftUI/TabBarMinimizeBehavior#topics)

### [Type Properties](/documentation/SwiftUI/TabBarMinimizeBehavior#Type-Properties)

[`static let automatic: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/automatic)Determine the behavior automatically based on the surrounding context.[`static let never: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/never)Never minimize the tab bar.[`static let onScrollDown: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/onscrolldown)Minimize the tab bar when downwards scrolling starts. Minimizing is supported for tab bars on only iPhone.[`static let onScrollUp: TabBarMinimizeBehavior`](/documentation/swiftui/tabbarminimizebehavior/onscrollup)Minimize the tab bar when upwards scrolling starts. Minimizing is supported for tab bars on only iPhone.## [Relationships](/documentation/SwiftUI/TabBarMinimizeBehavior#relationships)

### [Conforms To](/documentation/SwiftUI/TabBarMinimizeBehavior#conforms-to)

- [`Equatable`](/documentation/Swift/Equatable)

- [`Hashable`](/documentation/Swift/Hashable)

- [`Sendable`](/documentation/Swift/Sendable)

- [`SendableMetatype`](/documentation/Swift/SendableMetatype)

## [See Also](/documentation/SwiftUI/TabBarMinimizeBehavior#see-also)

### [Configuring a tab bar](/documentation/SwiftUI/TabBarMinimizeBehavior#Configuring-a-tab-bar)

[`func defaultAdaptableTabBarPlacement(AdaptableTabBarPlacement) -> some View`](/documentation/swiftui/view/defaultadaptabletabbarplacement(_:))Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.[`func tabViewSidebarHeader<Content>(content: () -> Content) -> some View`](/documentation/swiftui/view/tabviewsidebarheader(content:))Adds a custom header to the sidebar of a tab view.[`func tabViewSidebarFooter<Content>(content: () -> Content) -> some View`](/documentation/swiftui/view/tabviewsidebarfooter(content:))Adds a custom footer to the sidebar of a tab view.[`func tabViewSidebarBottomBar<Content>(content: () -> Content) -> some View`](/documentation/swiftui/view/tabviewsidebarbottombar(content:))Adds a custom bottom bar to the sidebar of a tab view.[`struct AdaptableTabBarPlacement`](/documentation/swiftui/adaptabletabbarplacement)A placement for tabs in a tab view using the adaptable sidebar style.[`var tabBarPlacement: TabBarPlacement?`](/documentation/swiftui/environmentvalues/tabbarplacement)The current placement of the tab bar.[`struct TabBarPlacement`](/documentation/swiftui/tabbarplacement)A placement for tabs in a tab view.[`var isTabBarShowingSections: Bool`](/documentation/swiftui/environmentvalues/istabbarshowingsections)A Boolean value that determines whether a tab view shows the expanded contents of a tab section.[`enum TabViewBottomAccessoryPlacement`](/documentation/swiftui/tabviewbottomaccessoryplacement)A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.