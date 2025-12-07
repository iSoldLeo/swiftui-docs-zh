--- 来源：https://developer.apple.com/documentation/SwiftUI/View/tabViewSidebarFooter(content:)

抓取时间：2025-12-02T17:29:43Z

---

# tabViewSidebarFooter(content:)

**实例方法**

为标签视图的侧边栏添加自定义页脚。

## 声明

```swift
nonisolated func tabViewSidebarFooter<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## 说明

页脚显示在侧边栏底部，位于所有标签之后，并可随内容滚动。页脚仅在 [TabView](../TabView.zh-Hans.md) 显示侧边栏时可见。

以下示例在侧边栏内容底部添加联系支持链接：

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }

    Tab("Browse", systemImage: "list.bullet") {
        MyBrowseView()
    }
}
.tabViewStyle(.sidebarAdaptable)
.tabViewSidebarFooter {
    ContactSupportLink()
}
```

## 配置标签栏

- **defaultAdaptableTabBarPlacement(_:)**：指定使用自适应侧边栏样式的标签视图中标签的默认位置。

- **tabViewSidebarHeader(content:)**：向标签视图的侧边栏添加自定义标题。

- **tabViewSidebarBottomBar(content:)**：向标签视图的侧边栏添加自定义底部栏。

- **AdaptableTabBarPlacement**：使用自适应侧边栏样式的标签视图中标签的位置。

- **tabBarPlacement**：标签栏的当前位置。

- **TabBarPlacement**：标签视图中标签的位置。

- **isTabBarShowingSections**：一个布尔值，用于确定选项卡视图是否显示选项卡部分的展开内容。

- **TabBarMinimizeBehavior**

- **TabViewBottomAccessoryPlacement**：选项卡视图中底部附件的位置。您可以根据位置调整附件视图的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/tabViewSidebarFooter(content:)
crawled: 2025-12-02T17:29:43Z
---

# tabViewSidebarFooter(content:)

**Instance Method**

Adds a custom footer to the sidebar of a tab view.

## Declaration

```swift
nonisolated func tabViewSidebarFooter<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## Discussion

The footer appears at the bottom of the sidebar after any tab labels and can scroll with the content. The footer is only visible when the [TabView](../TabView.zh-Hans.md) is displaying the sidebar.

The following example adds a link to contact support to the bottom of the sidebar content:

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }

    Tab("Browse", systemImage: "list.bullet") {
        MyBrowseView()
    }
}
.tabViewStyle(.sidebarAdaptable)
.tabViewSidebarFooter {
    ContactSupportLink()
}
```

## Configuring a tab bar

- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **AdaptableTabBarPlacement**: A placement for tabs in a tab view using the adaptable sidebar style.
- **tabBarPlacement**: The current placement of the tab bar.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**
- **TabViewBottomAccessoryPlacement**: A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

