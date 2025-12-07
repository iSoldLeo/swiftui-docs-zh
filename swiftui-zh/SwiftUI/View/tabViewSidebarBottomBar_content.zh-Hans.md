--- 来源：https://developer.apple.com/documentation/swiftui/view/tabviewsidebarbottombar(content:)

抓取时间：2025-12-03T05:59:57Z

---

# tabViewSidebarBottomBar(content:)

**实例方法**

为标签视图的侧边栏添加自定义底部栏。

## 声明

```swift
nonisolated func tabViewSidebarBottomBar<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## 说明

内容固定在侧边栏底部，因此侧边栏可见时，内容始终可见，且不会随内容滚动。

以下示例在侧边栏底部添加一个帐户按钮：

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
.tabViewSidebarBottomBar {
    AccountButton()
}
```

## 配置标签栏

- **defaultAdaptableTabBarPlacement(_:)**：指定使用自适应侧边栏样式的标签视图中标签的默认位置。

- **tabViewSidebarHeader(content:)**：为标签视图的侧边栏添加自定义标题。

- **tabViewSidebarFooter(content:)**：为标签视图的侧边栏添加自定义页脚。

- **AdaptableTabBarPlacement**：使用自适应侧边栏样式时，标签在标签视图中的位置。

- **tabBarPlacement**：标签栏的当前位置。

- **TabBarPlacement**：标签在标签视图中的位置。

- **isTabBarShowingSections**：一个布尔值，用于确定标签视图是否显示标签部分的展开内容。

- **TabBarMinimizeBehavior**

- **TabViewBottomAccessoryPlacement**：标签视图中底部附件的位置。您可以根据位置调整附件视图的内容。


---
source: https://developer.apple.com/documentation/swiftui/view/tabviewsidebarbottombar(content:)
crawled: 2025-12-03T05:59:57Z
---

# tabViewSidebarBottomBar(content:)

**Instance Method**

Adds a custom bottom bar to the sidebar of a tab view.

## Declaration

```swift
nonisolated func tabViewSidebarBottomBar<Content>(@ViewBuilder content: () -> Content) -> some View where Content : View

```

## Discussion

The content is pinned at the bottom of the sidebar, so it’s always visible when the sidebar is visible and doesn’t scroll with the content.

The following example adds an account button to the bottom of the sidebar:

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
.tabViewSidebarBottomBar {
    AccountButton()
}
```

## Configuring a tab bar

- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **AdaptableTabBarPlacement**: A placement for tabs in a tab view using the adaptable sidebar style.
- **tabBarPlacement**: The current placement of the tab bar.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**
- **TabViewBottomAccessoryPlacement**: A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

