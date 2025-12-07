--- 来源：https://developer.apple.com/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation

抓取时间：2025-12-02T15:51:13Z

---

# 使用标签导航增强应用内容 | Apple 开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ 导航 ](/documentation/swiftui/navigation)

- [ 使用标签导航增强应用内容 ](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation)

- [ 导航 ](/documentation/swiftui/navigation)

- 使用标签导航增强应用内容

示例代码# 使用标签导航增强应用内容

将应用内容置于中心位置，同时使用标签栏快速访问导航。[ 下载 (1.2 GB) ](https://docs-assets.developer.apple.com/published/08bd3c5ea0b3/DestinationVideo.zip)iOS 18.0+iPadOS 18.0+macOS 15.0+tvOS 18.0+vvOS 2.0+## [概述](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Overview)

[目标位置]视频](/documentation/visionOS/destination-video)采用了[`sidebarAdaptable`](/documentation/swiftui/tabviewstyle/sidebaradaptable)标签页样式，针对各个平台优化了内容浏览体验。

从iPadOS 18开始，标签栏不再位于屏幕底部，而是悬浮在屏幕顶部，覆盖在内容之上。这种设计营造了沉浸式的全屏浏览体验。标签栏为用户提供了应用的顶级导航。然而，过多的标签可能会让用户难以找到所需内容。使用侧边栏可以更轻松地浏览层级分明的详细信息。

视频包含自定义控件。内容描述：一段iPad版Destination Video的屏幕录像，展示了标签栏如何从侧边栏变为可编辑状态。 [播放](#)### [创建标签栏](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Create-a-tab-bar)

您可以使用 [`init(selection:content:)`](/documentation/swiftui/tabview/init(selection:content:)) 初始化器创建具有显式选择绑定的 [`TabView`](/documentation/swiftui/tabview)。要在 [`TabView`](`Tab`](/documentation/swiftui/tab) 中添加标签，请初始化 [`Tab`](/documentation/swiftui/tab)。 Destination Video 使用 [`init(_:systemImage:value:content:)`](/documentation/swiftui/tab/init(_:systemimage:value:content:)) 初始化器创建每个选项卡：

```
@State private var selectedTab: Tabs = .watchNow


var body: some View {
    TabView(selection: $selectedTab) {
        Tab("Watch Now", systemImage: "play", value: .watchNow) {
            WatchNowView()
        }
        // More tabs...
    }
}

```

`TabView` 的选择值类型与其包含的选项卡的值类型匹配。在本例中，每个 `Tab` 的值均为 `Tabs` 类型，此示例定义了以下枚举：

```
enum Tabs: Equatable, Hashable, Identifiable {
    case watchNow
    case library
    case new
    case favorites
    case search
}

```

注意

使用符号图像作为选项卡时，请使用轮廓变体。当选项卡栏中出现时，系统会自动选择填充变体。

此外，此示例使用了 [`search`](/documentation/swiftui/tabrole/search) 角色和 [`init(value:role:content:)`](/documentation/swiftui/tab/init(value:role:content:)) 初始化器。将标签角色设置为 `search` 后，系统会对 `Tab` 应用一些默认自定义设置。搜索标签将获得：

- 搜索的默认标题：“搜索”

- 搜索的默认系统图标，放大镜

- 搜索的默认固定行为，系统会自动将其固定在标签栏中

```
Tab(value: .search, role: .search) {
    // ...
}

```

固定标签会显示在标签栏的尾部，具体位置取决于应用程序的首选语言。如果语言是从左到右，则标签会显示在右侧；如果语言是从右到左，则标签会显示在左侧。

### [在标签视图中构建层级结构](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Build-hierarchy-in-tab-view)

您可以使用 [`TabSection`](/documentation/swiftui/tabsection) 在 `TabView` 内声明二级标签层级结构。例如，“目的地视频”使用 [`init(content:header:)`](/documentation/swiftui/tabsection/init(content:header:)) 初始化器来创建标签部分。

```
TabView(selection: $selectedTab) {
    Tab("Watch Now", systemImage: "play", value: .watchNow) {
        WatchNowView()
    }


    // More tabs...
    
    TabSection {
        Tab("Cinematic Shots", systemImage: "list.and.film", value: .collections(.cinematic)) {
            // ...
        }
    } header: {
        Label("Collections", systemImage: "folder")
    }
}

```

然后，它扩展了 `Tabs` 枚举以支持二级标签：

```
enum Tabs: Equatable, Hashable, Identifiable {
    case watchNow
    // ..
    case search
    case collections(Category)
    case animations(Category)
}


enum Category: Equatable, Hashable, Identifiable, CaseIterable {
    case cinematic
    case forest
    case sea
    // ...
}

```

此示例使用 [`ForEach`](/documentation/swiftui/foreach) 循环来迭代并为每个标签值初始化一个新的 `Tab`。

```
TabSection {
    ForEach(Category.collectionsList) { collection in
        Tab(collection.name, systemImage: collection.icon, value: Tabs.collections(collection)) {
            // ..
        }
    }
} header: {
    Label("Collections", systemImage: "folder")
}

```

### [使标签栏可自适应](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Make-the-tab-bar-adaptable)

使用 [`sidebarAdaptable`](/documentation/swiftui/tabviewstyle/sidebaradaptable) 样式的标签栏允许用户在侧边栏和标签栏之间切换。这样，您的应用既可以利用紧凑的标签栏快速导航到顶级目标位置的便利性，又可以在侧边栏中提供丰富的导航层级和目标选项。

要创建可自适应的标签栏，Destination Video 会在其 `TabView` 中添加 [`tabViewStyle(_:)`](/documentation/swiftui/view/tabviewstyle(_:)) 修饰符，并传入值 [`sidebarAdaptable`](/documentation/swiftui/tabviewstyle/sidebaradaptable)。

```
TabView(selection: $selectedTab) {
    // Tabs
    // ..
}
.tabViewStyle(.sidebarAdaptable)



```

样式为 `sidebarAdaptable` 的 `TabView` 在不同平台上的显示效果有所不同，如下图所示。

带有自定义控件的视频。内容描述：一段视频展示了 iPad 上标签栏如何演变为侧边栏。[播放](#) 在 iPadOS 中，`TabView` 会显示为顶部标签栏，并变为侧边栏。标签栏和侧边栏中均会显示标签部分。在紧凑视图中，`TabView` 会显示为底部标签栏。带有自定义控件的视频。内容描述：iOS 上标签视图的屏幕截图。[播放](#) 在 iOS 中，`TabView` 会显示为底部标签栏。标签栏中会显示辅助标签。与 iPadOS 不同，标签栏中不会显示标签标题。在 macOS 中，标签栏以侧边栏的形式显示。标签栏也会显示在侧边栏中。

带有自定义控件的视频。内容描述：一段展示 tvOS 标签视图的视频。[播放](#)在 tvOS 中，标签栏以侧边栏的形式显示，用户选择标签后，侧边栏会折叠成一个悬浮的胶囊状元素。标签栏也会显示在侧边栏中。带有自定义控件的视频。内容描述：一张展示 visionOS 标签视图的图片。[播放](#)在 visionOS 中，标签栏以装饰元素的形式显示。标签栏标题会显示在装饰元素中。如果在装饰框中选择标签栏标题，侧边栏将显示该标签栏中的标签。

默认情况下，在 iPadOS 中使用标签视图样式时，标签栏中的内容会滚动到侧边栏下方。您可以通过在标签栏中添加修饰符来阻止内容滚动到侧边栏下方。

### [启用自定义](⟦LU_0079)

标签视图自定义功能允许用户进入编辑模式并个性化标签栏。 Destination Video 的自定义功能允许用户：

- 拖放标签页，即可在标签栏中添加或移除标签页

- 隐藏非必要标签页

- 重新排列侧边栏标签页部分的标签页顺序

- 重新排列标签栏中的标签页顺序

为了启用自定义功能，此示例定义了一个 [`TabViewCustomization`](/documentation/swiftui/tabviewcustomization)，并使用 [`tabViewCustomization(_:)`](/documentation/swiftui/view/tabviewcustomization(_:)) 修饰符将其附加到 `TabView`。为了使自定义功能持久化，此示例添加了 [`AppStorage`](/documentation/swiftui/appstorage)，并为其指定了 `TabViewCustomization` 变量的标识符。最后，它会为每个标签页添加 [`customizationID(_:)`](/documentation/swiftui/tabcontent/customizationid(_:)) 修饰符。

```
@AppStorage("sidebarCustomizations") var tabViewCustomization: TabViewCustomization
@State private var selectedTab: Tabs = .watchNow


var body: some View {
    TabView(selection: $selectedTab) {
        Tab("Watch Now", systemImage: "play", value: .watchNow) {
            WatchNowView()
        }
        .customizationID(Tabs.watchNow.customizationID)


        // More tabs...


    }
    .tabViewCustomization($tabViewCustomization)
}

```

要保持最重要的标签页可见且位置固定，请使用 [`customizationBehavior(_:for:)`](/documentation/swiftui/tabcontent/customizationbehavior(_:for:)) 修饰符关闭这些标签页的自定义行为。

```
Tab("Watch Now", systemImage: "play", value: .watchNow) {
    WatchNowView()
}
.customizationBehavior(.disabled, for: .sidebar, .tabBar)

```

### [设置标签页的默认可见性](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Set-the-default-visibility-for-tabs)

在 iPadOS 中，如果标签页过多而无法全部显示在屏幕上，系统会折叠超出屏幕范围的标签页并启用滚动。但是，标签页过多会使用户难以找到所需的标签页，从而影响应用的导航。建议限制标签页的数量，使其全部显示在标签栏中。 [`defaultVisibility(_:for:)`](/documentation/swiftui/tabcontent/defaultvisibility(_:for:)) 修饰符设置 `Tab` 或 `TabSection` 的默认可见性。

目标视频包含五个标签页和两个标签页分区，每个标签页分区包含多个二级标签页，但标签栏中仅显示七个标签页。为了将标签栏限制为最重要的标签页，默认情况下，`TabSection` 内的所有标签页都会从标签栏中隐藏。

```
TabSection {
    // Tabs
} header {
    // Section header
}
.defaultVisibility(.hidden, for: .tabBar)

```

带有自定义控件的视频。内容描述：一段展示 iPad 上标签栏如何演变为侧边栏的视频。[播放](#)

带有自定义控件的视频。内容描述：一段展示 tvOS 上标签页视图的视频。 [播放](#)

如果启用自定义功能，[`defaultVisibility(_:for:)`](/documentation/swiftui/tabcontent/defaultvisibility(_:for:))修饰符仍然允许用户将标签从侧边栏拖到标签栏中。如果您希望标签仅显示在侧边栏中，请使用[`sidebarOnly`](/documentation/swiftui/tabplacement/sidebaronly)而不是设置默认可见性。

有关设计指南，请参阅“人机界面指南 > [标签栏](/design/Human-Interface-Guidelines/tab-bars)”。

## [另请参阅](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#See-Also)

#### [相关示例](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Related-samples)

[目标视频](/documentation/visionOS/destination-video)#### [相关文章](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Related-articles)

[使用标签栏和侧边栏提升您的 iPad 应用体验](/documentation/UIKit/elevating-your-ipad-app-with-a-tab-bar-and-sidebar)提供简洁、符合人体工学的标签栏，方便您快速访问应用的关键部分；同时提供侧边栏，方便您进行深度导航。#### [相关视频](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Related-videos)

[在 iPadOS 中提升您的标签栏和侧边栏体验](https://developer.apple.com/videos/play/wwdc2024/10147)

---
source: https://developer.apple.com/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation
crawled: 2025-12-02T15:51:13Z
---

# Enhancing your app’s content with tab navigation | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ Navigation ](/documentation/swiftui/navigation)

- [ Enhancing your app’s content with tab navigation ](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation)

- [ Navigation ](/documentation/swiftui/navigation)

-  Enhancing your app’s content with tab navigation 

Sample Code# Enhancing your app’s content with tab navigation

Keep your app content front and center while providing quick access to navigation using the tab bar.[ Download (1.2 GB) ](https://docs-assets.developer.apple.com/published/08bd3c5ea0b3/DestinationVideo.zip)iOS 18.0+iPadOS 18.0+macOS 15.0+tvOS 18.0+visionOS 2.0+## [Overview](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Overview)

[Destination Video](/documentation/visionOS/destination-video) adopts the [`sidebarAdaptable`](/documentation/swiftui/tabviewstyle/sidebaradaptable) tab view style, which optimizes the content browsing experience for each platform.

Starting in iPadOS 18, the tab bar appears on the top of the screen floating over your content instead of appearing at the bottom of the screen. This appearance creates an immersive full-screen browsing experience. Tab bars provide people with access to the top-level navigation in your app. However, too many tabs can make it hard for people to locate content. Implementing a sidebar makes it easier to navigate a detailed information hierarchy.

 Video with custom controls.  Content description: A screen recording of Destination Video on iPad that shows the tab bar turning into a sidebar, then becoming editable. [ Play ](#)### [Create a tab bar](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Create-a-tab-bar)

You can create a [`TabView`](/documentation/swiftui/tabview) with an explicit selection binding using the [`init(selection:content:)`](/documentation/swiftui/tabview/init(selection:content:)) initializer. To add a tab within a `TabView` initialize a [`Tab`](/documentation/swiftui/tab). Destination Video uses the [`init(_:systemImage:value:content:)`](/documentation/swiftui/tab/init(_:systemimage:value:content:)) initializer to create each tab:



```
@State private var selectedTab: Tabs = .watchNow


var body: some View {
    TabView(selection: $selectedTab) {
        Tab("Watch Now", systemImage: "play", value: .watchNow) {
            WatchNowView()
        }
        // More tabs...
    }
}

```

The selection value type of the `TabView` matches the value type of the tabs it contains. In this case, the value of each `Tab` is of type `Tabs`, which this sample defines the following enumeration:



```
enum Tabs: Equatable, Hashable, Identifiable {
    case watchNow
    case library
    case new
    case favorites
    case search
}

```

Note

When using symbol images for your tabs, use the outline variant. The system automatically selects the filled variant when it appears in a tab bar.

Additionally, this sample uses the [`search`](/documentation/swiftui/tabrole/search) role with the [`init(value:role:content:)`](/documentation/swiftui/tab/init(value:role:content:)) initializer. Setting the tab role to `search` makes the system applies a few default customizations to the `Tab`. The search tab gets:

- The default title for search, “search”

- The default system symbol for search, a magnifying glass

- The default pinned behavior for search, the system automatically pins it in the tab bar



```
Tab(value: .search, role: .search) {
    // ...
}

```

Pinned tabs appear at the trailing edge of the tab bar, depending on the preferred language of your app. When the language is a left-to-right language, they appear on the right side. When the language is a right-to-left language, they’re on the left side.

### [Build hierarchy in tab view](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Build-hierarchy-in-tab-view)

You can use a [`TabSection`](/documentation/swiftui/tabsection) to declare a secondary tab hierarchy within a `TabView`. For example Destination Video uses the [`init(content:header:)`](/documentation/swiftui/tabsection/init(content:header:)) initializer to create tab sections.



```
TabView(selection: $selectedTab) {
    Tab("Watch Now", systemImage: "play", value: .watchNow) {
        WatchNowView()
    }


    // More tabs...
    
    TabSection {
        Tab("Cinematic Shots", systemImage: "list.and.film", value: .collections(.cinematic)) {
            // ...
        }
    } header: {
        Label("Collections", systemImage: "folder")
    }
}

```

Then it extends the `Tabs` enumeration to account for secondary tabs:



```
enum Tabs: Equatable, Hashable, Identifiable {
    case watchNow
    // ..
    case search
    case collections(Category)
    case animations(Category)
}


enum Category: Equatable, Hashable, Identifiable, CaseIterable {
    case cinematic
    case forest
    case sea
    // ...
}

```

This sample uses a [`ForEach`](/documentation/swiftui/foreach) loop to iterate and initialize a new `Tab` for each tab value.



```
TabSection {
    ForEach(Category.collectionsList) { collection in
        Tab(collection.name, systemImage: collection.icon, value: Tabs.collections(collection)) {
            // ..
        }
    }
} header: {
    Label("Collections", systemImage: "folder")
}

```

### [Make the tab bar adaptable](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Make-the-tab-bar-adaptable)

Tab bars with the [`sidebarAdaptable`](/documentation/swiftui/tabviewstyle/sidebaradaptable) style allow people to toggle between the sidebar and tab bar. This lets your app leverage the convenience of being able to quickly navigate to top-level destinations within a compact tab bar while providing rich navigation hierarchy and destination options in the sidebar.

To create an adaptable tab bar, Destination Video adds the [`tabViewStyle(_:)`](/documentation/swiftui/view/tabviewstyle(_:)) modifier to its `TabView` and passes in the value [`sidebarAdaptable`](/documentation/swiftui/tabviewstyle/sidebaradaptable).



```
TabView(selection: $selectedTab) {
    // Tabs
    // ..
}
.tabViewStyle(.sidebarAdaptable)



```

A `TabView` with the `sidebarAdaptable` style appears differently depending on the platform, as shown in the following images.

 Video with custom controls.  Content description: A video that shows a tab bar morphing into a sidebar on iPad. [ Play ](#)A `TabView` appears as top tab bar that becomes a sidebar in iPadOS. Tab sections appear in both the sidebar and the tab bar. In compact view, a `TabView` appears as a bottom tab bar. Video with custom controls.  Content description: A screenshot of tab view on iOS. [ Play ](#)A `TabView` appears as a bottom tab bar in iOS. Secondary tabs appear in the tab bar. Unlike iPadOS, the section header doesn’t appear in the tab bar.A `TabView` appears as a sidebar in macOS. Tab sections also appear in the sidebar.

 Video with custom controls.  Content description: A video that shows tab view on tvOS. [ Play ](#)A `TabView` appears as a sidebar that collapses into a floating pill after a person selects a tab in tvOS. Tab sections appear in the sidebar. Video with custom controls.  Content description: An image that shows tab view on visionOS. [ Play ](#)A `TabView` appears as an ornament in visionOS. Tab section headers appear in the ornament. If you select a tab section header in the ornament, the sidebar displays the tabs in that section.Note

By default, contents in a `ScrollView(.horizontal)` scroll under the sidebar when you use the `sidebarAdaptable` tab view style in iPadOS. You can prevent the content from scrolling under the sidebar by adding the [`clipped(antialiased:)`](/documentation/swiftui/view/clipped(antialiased:)) or [`clipShape(_:style:)`](/documentation/swiftui/view/clipshape(_:style:)) modifier to `ScrollView`.

### [Enable customization](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Enable-customization)

Tab view customization allows people to enter edit mode and personalize the tab bar. The customization in Destination Video allows people to:

- Drag and drop tabs to remove and add tabs to the tab bar

- Hide non-essential tabs

- Reorder tabs in tab sections in the sidebar

- Reorder tabs in the tab bar

To enable customizations, this sample defines a [`TabViewCustomization`](/documentation/swiftui/tabviewcustomization) and attaches it to the `TabView` using the [`tabViewCustomization(_:)`](/documentation/swiftui/view/tabviewcustomization(_:)) modifier. To persist the customization, this sample adds [`AppStorage`](/documentation/swiftui/appstorage) with an identifier for a `TabViewCustomization` variable. Finally, it adds the [`customizationID(_:)`](/documentation/swiftui/tabcontent/customizationid(_:)) modifier to each tab.



```
@AppStorage("sidebarCustomizations") var tabViewCustomization: TabViewCustomization
@State private var selectedTab: Tabs = .watchNow


var body: some View {
    TabView(selection: $selectedTab) {
        Tab("Watch Now", systemImage: "play", value: .watchNow) {
            WatchNowView()
        }
        .customizationID(Tabs.watchNow.customizationID)


        // More tabs...


    }
    .tabViewCustomization($tabViewCustomization)
}

```

To keep the most important tabs visible and in a fixed position, turn off customization behavior for those tabs using the [`customizationBehavior(_:for:)`](/documentation/swiftui/tabcontent/customizationbehavior(_:for:)) modifier.



```
Tab("Watch Now", systemImage: "play", value: .watchNow) {
    WatchNowView()
}
.customizationBehavior(.disabled, for: .sidebar, .tabBar)

```



### [Set the default visibility for tabs](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Set-the-default-visibility-for-tabs)

In iPadOS, if there are too many tabs to fit in the screen, the system collapses the tabs that don’t fit and enables scrolling. However, having too many tabs can make it harder for people to locate the tab they’re looking for and navigate your app. Consider limiting the number of tabs so they all fit in the tab bar. The [`defaultVisibility(_:for:)`](/documentation/swiftui/tabcontent/defaultvisibility(_:for:)) modifier sets the default visibility of a `Tab` or `TabSection`.

Destination Video contains five tabs and two tab sections, each tab section contains multiple secondary tabs, but only seven tabs appear in the tab bar. In order to limit the tab bar to the most important tabs, all tabs within a `TabSection` are hidden from the tab bar by default.



```
TabSection {
    // Tabs
} header {
    // Section header
}
.defaultVisibility(.hidden, for: .tabBar)

```

 Video with custom controls.  Content description: A video that shows a tab bar morphing into a sidebar on iPad. [ Play ](#)

 Video with custom controls.  Content description: A video that shows tab view on tvOS. [ Play ](#)

If you enable customization, the [`defaultVisibility(_:for:)`](/documentation/swiftui/tabcontent/defaultvisibility(_:for:)) modifier still allows people to drag a tab from the sidebar into the tab bar. If you want to restrict tabs to only appear in the sidebar use [`sidebarOnly`](/documentation/swiftui/tabplacement/sidebaronly) instead of setting the default visibility.

For design guidance, see Human Interface Guidelines > [Tab bars](/design/Human-Interface-Guidelines/tab-bars).

## [See Also](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#See-Also)

#### [Related samples](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Related-samples)

[ Destination Video ](/documentation/visionOS/destination-video)#### [Related articles](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Related-articles)

[Elevating your iPad app with a tab bar and sidebar](/documentation/UIKit/elevating-your-ipad-app-with-a-tab-bar-and-sidebar)Provide a compact, ergonomic tab bar for quick access to key parts of your app, and a sidebar for in-depth navigation.#### [Related videos](/documentation/SwiftUI/Enhancing-your-app-content-with-tab-navigation#Related-videos)

[ Elevate your tab and sidebar experience in iPadOS ](https://developer.apple.com/videos/play/wwdc2024/10147)