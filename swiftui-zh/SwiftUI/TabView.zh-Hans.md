--- 来源：https://developer.apple.com/documentation/SwiftUI/TabView
抓取时间：2025-12-02T16:23:26Z

---

# TabView

**Structure**

一个使用交互式用户界面元素在多个子视图之间切换的视图。

## 声明

```swift
struct TabView<SelectionValue, Content> where SelectionValue : Hashable, Content : View
```

## 概述

要创建带有标签的用户界面，请将 [Tab](Tab.zh-Hans.md) 放置在 `TabView` 中。在 iOS 上，您还可以使用徽章修饰符（例如 [badge(_:)](TabContent/badge.zh-Hans.md)）为每个标签分配一个徽章。

以下示例创建了一个包含三个标签的标签视图，每个标签都显示一个自定义子视图。第一个标签带有数字徽章，第三个标签带有字符串徽章。

```swift
TabView {
    Tab("Received", systemImage: "tray.and.arrow.down.fill") {
        ReceivedView()
    }
    .badge(2)

    Tab("Sent", systemImage: "tray.and.arrow.up.fill") {
        SentView()
    }

    Tab("Account", systemImage: "person.crop.circle.fill") {
        AccountView()
    }
    .badge("!")
}
```

要以编程方式选择不同的选项卡，请使用 [init(selection:content:)](TabView/init_selection_content.zh-Hans.md) 初始化器。您可以使用接受一个值的 `Tab` 初始化器为每个选项卡分配一个选择值。每个选项卡都应具有唯一的选择值，并且所有选项卡应具有相同的选择值类型。当用户在选项卡视图中选择一个选项卡时，选项卡视图会将选择绑定更新为当前所选选项卡的值。

以下示例创建了一个支持编程选择且包含 3 个选项卡的选项卡视图。

```swift
TabView(selection: $selection) {
    Tab("Received", systemImage: "tray.and.arrow.down.fill", value: 0) {
        ReceivedView()
    }

    Tab("Sent", systemImage: "tray.and.arrow.up.fill", value: 1) {
        SentView()
    }

    Tab("Account", systemImage: "person.crop.circle.fill", value: 2) {
        AccountView()
    }
}
```

您可以使用 [page](TabViewStyle/page.zh-Hans.md) 样式来显示具有多个滚动内容页面的选项卡视图。

以下示例使用 `ForEach` 创建一个滚动选项卡视图，用于显示各个城市的温度。

```swift
TabView {
    ForEach(cities) { city in
        TemperatureView(city)
    }
}
.tabViewStyle(.page)
```

### 使用标签页分区

[sidebarAdaptable](TabViewStyle/sidebarAdaptable.zh-Hans.md) 样式支持通过使用 [TabSection](TabSection.zh-Hans.md) 将标签页分组来声明二级标签页层级结构。

在 iPadOS 上，标签页分区会同时显示在侧边栏和标签栏中。在 iOS 和 iPadOS 的横向紧凑尺寸模式下，二级标签页会显示在标签栏中。当二级标签页显示在标签栏中时，分区标题不会显示在标签栏中。建议限制 iOS 和 iPadOS 横向紧凑尺寸模式下的标签页数量，以便所有标签页都能显示在标签栏中。

以下示例包含 5 个标签页，其中 3 个标签页被分组在一个 [TabSection](TabSection.zh-Hans.md) 中。

```swift
TabView {
    Tab("Requests", systemImage: "paperplane") {
        RequestsView()
    }

    Tab("Account", systemImage: "person.crop.circle.fill") {
        AccountView()
    }

    TabSection("Messages") {
        Tab("Received", systemImage: "tray.and.arrow.down.fill") {
            ReceivedView()
        }

        Tab("Sent", systemImage: "tray.and.arrow.up.fill") {
            SentView()
        }

        Tab("Drafts", systemImage: "pencil") {
            DraftsView()
        }
    }
}
.tabViewStyle(.sidebarAdaptable)
```

### 切换水平和常规尺寸类别的标签页结构

以下示例展示了一个 `TabView`，其中紧凑模式下有 4 个标签页，常规模式下有 5 个标签页。在紧凑模式下，其中一个标签页是“浏览”标签页，它显示一个自定义列表视图。该列表视图允许用户导航到水平常规尺寸类别中“媒体库”和“播放列表”部分内的目标位置。当标签页数量发生变化时，导航路径和选择状态也会随之更新。

```swift
struct BrowseTabExample: View {
    @Environment(\.horizontalSizeClass) var sizeClass

    @State var selection: MusicTab = .listenNow
    @State var browseTabPath: [MusicTab] = []
    @State var playlists = [Playlist("All Playlists"), Playlist("Running")]

    var body: some View {
            TabView(selection: $selection) {
                Tab("Listen Now", systemImage: "play.circle", value: .listenNow) {
                    ListenNowView()
                }

                Tab("Radio", systemImage: "dot.radiowaves.left.and.right", value: .radio) {
                    RadioView()
                }

                Tab("Search", systemImage: "magnifyingglass", value: .search) {
                    SearchDetailView()
                }

                Tab("Browse", systemImage: "list.bullet", value: .browse) {
                    LibraryView(path: $browseTabPath)
                }
                .hidden(sizeClass != .compact)

                TabSection("Library") {
                    Tab("Recently Added", systemImage: "clock", value: MusicTab.library(.recentlyAdded)) {
                        RecentlyAddedView()
                    }

                    Tab("Artists", systemImage: "music.mic", value: MusicTab.library(.artists)) {
                        ArtistsView()
                    }
                }
                .hidden(sizeClass == .compact)

                TabSection("Playlists") {
                    ForEach(playlists) { playlist in
                        Tab(playlist.name, image: playlist.image, value: MusicTab.playlists(playlist)) {
                            playlist.detailView()
                        }
                    }
                }
                .hidden(sizeClass == .compact)
            }
            .tabViewStyle(.sidebarAdaptable)
            .onChange(of: sizeClass, initial: true) { _, sizeClass in
                if sizeClass == .compact && selection.showInBrowseTab {
                    browseTabPath = [selection]
                    selection = .browse
                } else if sizeClass == .regular && selection == .browse {
                    selection = browseTabPath.last ?? .library(.recentlyAdded)
                }
            }
        }
    }
}

struct LibraryView: View {
    @Binding var path: [MusicTab]

    var body: some View {
        NavigationStack(path: $path) {
            List {
                ForEach(MusicLibraryTab.allCases, id: \.self) { tab in
                    NavigationLink(tab.rawValue, value: MusicTab.library(tab))
                }
                // Code to add playlists here
            }
            .navigationDestination(for: MusicTab.self) { tab in
                tab.detail()
            }
        }
    }
}
```

### 添加自定义支持

您可以使用带有 [tabViewCustomization(_:)](View/tabViewCustomization.zh-Hans.md) 修饰符的 `sidebarAdaptable` 样式，允许用户自定义 `TabView` 中的标签页。自定义功能允许用户将标签从侧边栏拖到标签栏，隐藏标签，以及在侧边栏中重新排列标签。

所有支持自定义的标签和标签部分都需要一个自定义 ID。您可以使用 [customizationBehavior(_:for:)](TabContent/customizationBehavior___for.zh-Hans.md) 在所有可调整的标签栏位置中指定 [disabled](TabCustomizationBehavior/disabled.zh-Hans.md) 行为，将标签标记为不可自定义。

在 macOS 上，系统提供了重新排列标签部分的默认交互方式，但没有提供控制单个标签可见性的默认交互方式。如果需要自定义体验，可以通过在自定义设置中设置标签的可见性来实现。

您可以使用 `@AppStorage` 或 `@SceneStorage` 自动保存用户所做的任何可见性或标签部分顺序的自定义设置。

以下示例支持自定义标签视图中的所有 4 个标签，并使用 `@AppStorage` 保存用户所做的自定义设置。

```swift
@AppStorage
private var customization: TabViewCustomization

TabView {
    Tab("Home", systemImage: "house") {
        MyHomeView()
    }
    .customizationID("com.myApp.home")

    Tab("Reports", systemImage: "chart.bar") {
        MyReportsView()
    }
    .customizationID("com.myApp.reports")

    TabSection("Categories") {
        Tab("Climate", systemImage: "fan") {
            ClimateView()
        }
        .customizationID("com.myApp.climate")

        Tab("Lights", systemImage: "lightbulb") {
            LightsView()
        }
        .customizationID("com.myApp.lights")
    }
    .customizationID("com.myApp.browse")
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```

## 创建标签视图

- **init(content:)**：创建一个使用构建器创建标签的标签视图。

- **init(selection:content:)**：创建一个使用构建器创建标签并指定标签选择值的标签视图。

## 配置搜索激活

- **TabSearchActivation**：配置搜索标签页中搜索的激活行为。

## 在标签页中呈现视图

- **使用标签导航增强应用内容**：将应用内容置于中心位置，同时使用标签栏快速访问导航。

- **Tab**：标签视图中标签的内容及其关联的标签项。

- **TabRole**：定义标签用途的值。

- **TabSection**：一个可用于在选项卡视图中添加层级结构的容器。

- **tabViewStyle(_:)**：设置当前环境中选项卡视图的样式。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/TabView
crawled: 2025-12-02T16:23:26Z
---

# TabView

**Structure**

A view that switches between multiple child views using interactive user interface elements.

## Declaration

```swift
struct TabView<SelectionValue, Content> where SelectionValue : Hashable, Content : View
```

## Overview

To create a user interface with tabs, place [Tab](Tab.zh-Hans.md)s  in a `TabView`. On iOS, you can also use one of the badge modifiers, like [badge(_:)](TabContent/badge.zh-Hans.md), to assign a badge to each of the tabs.

The following example creates a tab view with three tabs, each presenting a custom child view. The first tab has a numeric badge and the third has a string badge.

```swift
TabView {
    Tab("Received", systemImage: "tray.and.arrow.down.fill") {
        ReceivedView()
    }
    .badge(2)

    Tab("Sent", systemImage: "tray.and.arrow.up.fill") {
        SentView()
    }

    Tab("Account", systemImage: "person.crop.circle.fill") {
        AccountView()
    }
    .badge("!")
}
```



To programmatically select different tabs, use the [init(selection:content:)](TabView/init_selection_content.zh-Hans.md) initializer. You can assign a selection value to each tab using a `Tab` initializer that takes a value. Each tab should have a unique selection value and all tabs should have the same selection value type. When people select a tab in the tab view, the tab view updates the selection binding to the value of the currently selected tab.

The following example creates a tab view that supports programatic selection and has 3 tabs.

```swift
TabView(selection: $selection) {
    Tab("Received", systemImage: "tray.and.arrow.down.fill", value: 0) {
        ReceivedView()
    }

    Tab("Sent", systemImage: "tray.and.arrow.up.fill", value: 1) {
        SentView()
    }

    Tab("Account", systemImage: "person.crop.circle.fill", value: 2) {
        AccountView()
    }
}
```

You can use the [page](TabViewStyle/page.zh-Hans.md) style to display a tab view with multiple scrolling pages of content.

The following example uses a `ForEach` to create a scrolling tab view that shows the temperatures of various cities.

```swift
TabView {
    ForEach(cities) { city in
        TemperatureView(city)
    }
}
.tabViewStyle(.page)
```

### Using tab sections

The [sidebarAdaptable](TabViewStyle/sidebarAdaptable.zh-Hans.md) style supports declaring a secondary tab hierarchy by grouping tabs with a [TabSection](TabSection.zh-Hans.md).

On iPadOS, tab sections appear in both the sidebar and the tab bar. On iOS and the horizontally compact size class on iPadOS, secondary tabs appear in the tab bar. When secondary tabs appear in the tab bar, the section header doesn’t appear in the tab bar. Consider limiting the number of tabs on iOS and the iPadOS horizontal compact size class so all tabs fit in the tab bar.

The following example has 5 tabs, three of which are grouped within a [TabSection](TabSection.zh-Hans.md).

```swift
TabView {
    Tab("Requests", systemImage: "paperplane") {
        RequestsView()
    }

    Tab("Account", systemImage: "person.crop.circle.fill") {
        AccountView()
    }

    TabSection("Messages") {
        Tab("Received", systemImage: "tray.and.arrow.down.fill") {
            ReceivedView()
        }

        Tab("Sent", systemImage: "tray.and.arrow.up.fill") {
            SentView()
        }

        Tab("Drafts", systemImage: "pencil") {
            DraftsView()
        }
    }
}
.tabViewStyle(.sidebarAdaptable)
```

### Changing tab structure between horizontal and regular size classes

The following example shows a `TabView` with 4 tabs in compact and 5 tabs in regular. In compact, one of the tabs is a ‘Browse’ tab that displays a custom list view. This list view allows navigating to the destinations that are contained within the ‘Library’ and ‘Playlists’ sections in the horizontally regular size class. The navigation path and the selection state are updated when the number of tabs changes.

```swift
struct BrowseTabExample: View {
    @Environment(\.horizontalSizeClass) var sizeClass

    @State var selection: MusicTab = .listenNow
    @State var browseTabPath: [MusicTab] = []
    @State var playlists = [Playlist("All Playlists"), Playlist("Running")]

    var body: some View {
            TabView(selection: $selection) {
                Tab("Listen Now", systemImage: "play.circle", value: .listenNow) {
                    ListenNowView()
                }

                Tab("Radio", systemImage: "dot.radiowaves.left.and.right", value: .radio) {
                    RadioView()
                }

                Tab("Search", systemImage: "magnifyingglass", value: .search) {
                    SearchDetailView()
                }

                Tab("Browse", systemImage: "list.bullet", value: .browse) {
                    LibraryView(path: $browseTabPath)
                }
                .hidden(sizeClass != .compact)

                TabSection("Library") {
                    Tab("Recently Added", systemImage: "clock", value: MusicTab.library(.recentlyAdded)) {
                        RecentlyAddedView()
                    }

                    Tab("Artists", systemImage: "music.mic", value: MusicTab.library(.artists)) {
                        ArtistsView()
                    }
                }
                .hidden(sizeClass == .compact)

                TabSection("Playlists") {
                    ForEach(playlists) { playlist in
                        Tab(playlist.name, image: playlist.image, value: MusicTab.playlists(playlist)) {
                            playlist.detailView()
                        }
                    }
                }
                .hidden(sizeClass == .compact)
            }
            .tabViewStyle(.sidebarAdaptable)
            .onChange(of: sizeClass, initial: true) { _, sizeClass in
                if sizeClass == .compact && selection.showInBrowseTab {
                    browseTabPath = [selection]
                    selection = .browse
                } else if sizeClass == .regular && selection == .browse {
                    selection = browseTabPath.last ?? .library(.recentlyAdded)
                }
            }
        }
    }
}

struct LibraryView: View {
    @Binding var path: [MusicTab]

    var body: some View {
        NavigationStack(path: $path) {
            List {
                ForEach(MusicLibraryTab.allCases, id: \.self) { tab in
                    NavigationLink(tab.rawValue, value: MusicTab.library(tab))
                }
                // Code to add playlists here
            }
            .navigationDestination(for: MusicTab.self) { tab in
                tab.detail()
            }
        }
    }
}
```

### Adding support for customization

You can allow people to customize the tabs in a `TabView` by using `sidebarAdaptable` style with the [tabViewCustomization(_:)](View/tabViewCustomization.zh-Hans.md) modifier. Customization allows people to drag tabs from the sidebar to the tab bar, hide tabs, and rearrange tabs in the sidebar.

All tabs and tab sections that support customization need to have a customization ID. You can mark a tab as being non-customizable by specifying a [disabled](TabCustomizationBehavior/disabled.zh-Hans.md) behavior in all adaptable tab bar placements using [customizationBehavior(_:for:)](TabContent/customizationBehavior___for.zh-Hans.md).

On macOS, a default interaction is provided for reordering sections but not for controlling the visibility of individual tabs. A custom experience should be provided if desired by setting the visibility of the tab on the customization.

You can use `@AppStorage` or `@SceneStorage` to automatically persist any visibility or section order customizations a person makes.

The following example supports customizing all 4 tabs in the tab view and uses `@AppStorage` to persist the customizations a person makes.

```swift
@AppStorage
private var customization: TabViewCustomization

TabView {
    Tab("Home", systemImage: "house") {
        MyHomeView()
    }
    .customizationID("com.myApp.home")

    Tab("Reports", systemImage: "chart.bar") {
        MyReportsView()
    }
    .customizationID("com.myApp.reports")

    TabSection("Categories") {
        Tab("Climate", systemImage: "fan") {
            ClimateView()
        }
        .customizationID("com.myApp.climate")

        Tab("Lights", systemImage: "lightbulb") {
            LightsView()
        }
        .customizationID("com.myApp.lights")
    }
    .customizationID("com.myApp.browse")
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```

## Creating a tab view

- **init(content:)**: Creates a tab view that uses a builder to create its tabs.
- **init(selection:content:)**: Creates a tab view that uses a builder to create and specify selection values for its tabs.

## Configuring search activation

- **TabSearchActivation**: Configures the activation behavior of search in the search tab.

## Presenting views in tabs

- **Enhancing your app’s content with tab navigation**: Keep your app content front and center while providing quick access to navigation using the tab bar.
- **Tab**: The content for a tab and the tab’s associated tab item in a tab view.
- **TabRole**: A value that defines the purpose of the tab.
- **TabSection**: A container that you can use to add hierarchy within a tab view.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.

## Conforms To

- View

