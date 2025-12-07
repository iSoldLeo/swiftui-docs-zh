--- 来源：https://developer.apple.com/documentation/SwiftUI/View/defaultAdaptableTabBarPlacement(_:)

抓取时间：2025-12-02T17:29:41Z

---

# defaultAdaptableTabBarPlacement(_:)

**实例方法**

指定使用自适应侧边栏样式的标签视图中标签的默认位置。

## 声明

```swift
nonisolated func defaultAdaptableTabBarPlacement(_ defaultPlacement: AdaptableTabBarPlacement = .automatic) -> some View

```

## 参数

- **defaultPlacement**：标签视图的默认排列方式。

## 说明

此修饰符仅在 iPadOS 的 [sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md) 样式中有效。在任何其他配置中，系统都会忽略它。

以下示例展示了一个包含三个标签页的 [TabView](../TabView.zh-Hans.md)，其中标签页视图在应用首次启动时会显示侧边栏。

```swift
TabView(selection: $selection) {
    Tab("Home", systemImage: "house", value: MyTab.home) {
        MyHomeView()
    }

    Tab("Downloads", systemImage: "square.and.arrow.down.fill",
        value: MyTab.downloads
    ) {
        MyDownloadsView()
    }

    Tab("Browse", systemImage: "list.bullet", value: MyTab.browse) {
        MyBrowseView()
    }
}
.tabViewStyle(.sidebarAdaptable)
.defaultAdaptableTabBarPlacement(.sidebar)
```

## 配置标签栏

- **tabViewSidebarHeader(content:)**：为标签页视图的侧边栏添加自定义标题。

- **tabViewSidebarFooter(content:)**：为标签页视图的侧边栏添加自定义页脚。

- **tabViewSidebarBottomBar(content:)**：为标签页视图的侧边栏添加自定义底部栏。

- **AdaptableTabBarPlacement**：使用自适应侧边栏样式时，标签页在标签页视图中的位置。

- **tabBarPlacement**：标签栏的当前位置。

- **TabBarPlacement**：标签页视图中标签页的位置。

- **isTabBarShowingSections**：一个布尔值，用于确定选项卡视图是否显示选项卡部分的展开内容。

- **TabBarMinimizeBehavior**

- **TabViewBottomAccessoryPlacement**：选项卡视图中底部附件的位置。您可以根据位置调整附件视图的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/View/defaultAdaptableTabBarPlacement(_:)
crawled: 2025-12-02T17:29:41Z
---

# defaultAdaptableTabBarPlacement(_:)

**Instance Method**

Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.

## Declaration

```swift
nonisolated func defaultAdaptableTabBarPlacement(_ defaultPlacement: AdaptableTabBarPlacement = .automatic) -> some View

```

## Parameters

- **defaultPlacement**: The default arrangement for the tab view.

## Discussion

This modifier is only effective on iPadOS in the [sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md) style. In any other configuration, the system ignores it.

The following example shows a [TabView](../TabView.zh-Hans.md) with three tabs, where the tab view displays the sidebar representation when the app initially launches.

```swift
TabView(selection: $selection) {
    Tab("Home", systemImage: "house", value: MyTab.home) {
        MyHomeView()
    }

    Tab("Downloads", systemImage: "square.and.arrow.down.fill",
        value: MyTab.downloads
    ) {
        MyDownloadsView()
    }

    Tab("Browse", systemImage: "list.bullet", value: MyTab.browse) {
        MyBrowseView()
    }
}
.tabViewStyle(.sidebarAdaptable)
.defaultAdaptableTabBarPlacement(.sidebar)
```

## Configuring a tab bar

- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **AdaptableTabBarPlacement**: A placement for tabs in a tab view using the adaptable sidebar style.
- **tabBarPlacement**: The current placement of the tab bar.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**
- **TabViewBottomAccessoryPlacement**: A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

