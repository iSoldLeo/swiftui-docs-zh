--- 来源：https://developer.apple.com/documentation/SwiftUI/View/contentToolbar(for:content:)

抓取时间：2025-11-30T21:08:32Z

---

# contentToolbar(for:content:)

**实例方法**

使用您提供的视图填充指定内容视图类型的工具栏。

## 声明

```swift
nonisolated func contentToolbar<Content>(for placement: ContentToolbarPlacement, @ToolbarContentBuilder content: () -> Content) -> some View where Content : ToolbarContent

```

## 参数

- **content**：表示工具栏内容的视图。

## 说明

使用此修饰符可添加与内容视图无关的工具栏内容。如果工具栏内容取决于当前显示的内容视图，请在内容视图中使用 `toolbar` 修饰符。

与配置被修改视图容器工具栏的工具栏修饰符不同，`contentToolbar` 修饰符配置的是被修改视图内容内部的工具栏。这意味着 `contentToolbar` 修饰符通常应直接应用于容器视图，而不是应用于容器视图内部的内容。例如，要配置选项卡视图侧边栏的工具栏，应将 `contentToolbar` 修饰符应用于 `TabView` 本身，而不是应用于 `TabView` 内的任何选项卡。

内容工具栏修饰符需要一个工具栏项集合，您可以通过两种方式提供该集合：一种是提供一个视图集合，其中每个视图都包含在 [ToolbarItem](../ToolbarItem.zh-Hans.md) 中；另一种是提供一个视图集合，并将其作为 [ToolbarItemGroup](../ToolbarItemGroup.zh-Hans.md) 提供。以下示例在标签页视图侧边栏底部添加了账户摘要，并在标签页视图侧边栏溢出菜单中添加了一个按钮。

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }

    TabSection("Categories") {
        Tab("Climate", systemImage: "fan") {
            ClimateView()
        }

        Tab("Lights", systemImage: "lightbulb") {
            LightsView()
        }
    }
}
.tabViewStyle(.sidebarAdaptable)
.contentToolbar(for: .tabViewSidebar) {
    ToolbarItem(placement: .automatic) {
        DisconnectDevicesButton()
    }
    ToolbarItem(placement: .bottomBar) {
        AccountSummaryView()
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/contentToolbar(for:content:)
crawled: 2025-11-30T21:08:32Z
---

# contentToolbar(for:content:)

**Instance Method**

Populates the toolbar of the specified content view type with the views you provide.

## Declaration

```swift
nonisolated func contentToolbar<Content>(for placement: ContentToolbarPlacement, @ToolbarContentBuilder content: () -> Content) -> some View where Content : ToolbarContent

```

## Parameters

- **content**: The views representing the content of the toolbar.

## Discussion

Use this modifier to add toolbar content that remains consistent regardless of the content view. Use a `toolbar` modifier within the content view if the toolbar content is dependent the content view is showing.

Unlike the toolbar modifier, which configures the toolbar of the modified view’s container, the `contentToolbar` modifier configures the toolbar within the modified view’s content instead. This means that the `contentToolbar` modifier should generally be applied directly to a container view, instead of to the content within a container view. For example, to configure the toolbar of tab view’s sidebar, apply the `contentToolbar` modifier to the `TabView` itself, not to any of the tabs within the `TabView`.

The content toolbar modifier expects a collection of toolbar items that you can provide by either supplying a collection of views with each view wrapped in a [ToolbarItem](../ToolbarItem.zh-Hans.md), or by providing a collection of views as a [ToolbarItemGroup](../ToolbarItemGroup.zh-Hans.md). The example below adds an account summary to the bottom of the tab view sidebar and a button to the tab view sidebar overflow menu.

```swift
TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }

    TabSection("Categories") {
        Tab("Climate", systemImage: "fan") {
            ClimateView()
        }

        Tab("Lights", systemImage: "lightbulb") {
            LightsView()
        }
    }
}
.tabViewStyle(.sidebarAdaptable)
.contentToolbar(for: .tabViewSidebar) {
    ToolbarItem(placement: .automatic) {
        DisconnectDevicesButton()
    }
    ToolbarItem(placement: .bottomBar) {
        AccountSummaryView()
    }
}
```

