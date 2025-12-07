---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/defaultVisibility(_:for:)
抓取时间： 2025-12-01T10:50:46Z
---

# defaultVisibility(_:for:)

**实例方法**

配置可定制上下文中标签页的默认可见性。

## 声明

```swift
nonisolated func defaultVisibility(_ visibility: Visibility, for placements: AdaptableTabBarPlacement...) -> some TabContent<Self.TabValue>

```

## 参数

- **visibility**：选项卡的可见性。
- **placements**：要应用可见性的位置。

## 讨论

[sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md)样式支持自定义 iPad 上的标签栏和侧边栏。要启用自定义功能，请使用[tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md)将[TabView](../TabView.zh-Hans.md)附加到[TabViewCustomization](../TabViewCustomization.zh-Hans.md)。

此修改器对其他平台或不支持自定义的[TabViewStyle](../TabViewStyle.zh-Hans.md) 没有影响。



下例显示的`TabView` 有三个标签页，其中一个默认隐藏在侧边栏中。

```swift
@AppStorage("MyAppTabViewCustomization")
private var customization: TabViewCustomization

TabView(selection: $selection) {
    Tab("Home", systemImage: "house", value: MyTab.home) {
        MyHomeView()
    }
    .customizationID("com.myApp.home")

    Tab("Reports", systemImage: "chart.bar", value: MyTab.reports) {
        MyReportsView()
    }
    .customizationID("com.myApp.reports")

    Tab("Browse", systemImage: "list.bullet", value: MyTab.browse) {
        MyBrowseView()
    }
    .customizationID("com.myApp.browse")
    .defaultVisibility(.hidden, for: .sidebar)
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/defaultVisibility(_:for:)
crawled: 2025-12-01T10:50:46Z
---

# defaultVisibility(_:for:)

**Instance Method**

Configures the default visibility of a tab in customizable contexts.

## Declaration

```swift
nonisolated func defaultVisibility(_ visibility: Visibility, for placements: AdaptableTabBarPlacement...) -> some TabContent<Self.TabValue>

```

## Parameters

- **visibility**: The tab’s visibility.
- **placements**: The locations to apply the visibility.

## Discussion

The [sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md) style supports customization of the tab bar and sidebar on iPad. To enable customization, attach a [TabViewCustomization](../TabViewCustomization.zh-Hans.md) to the [TabView](../TabView.zh-Hans.md) using [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md).

This modifier has no effect on other platforms or on a [TabViewStyle](../TabViewStyle.zh-Hans.md) that doesn’t support customization.



The following example shows a `TabView` with three tabs, one of which is hidden by default in the sidebar.

```swift
@AppStorage("MyAppTabViewCustomization")
private var customization: TabViewCustomization

TabView(selection: $selection) {
    Tab("Home", systemImage: "house", value: MyTab.home) {
        MyHomeView()
    }
    .customizationID("com.myApp.home")

    Tab("Reports", systemImage: "chart.bar", value: MyTab.reports) {
        MyReportsView()
    }
    .customizationID("com.myApp.reports")

    Tab("Browse", systemImage: "list.bullet", value: MyTab.browse) {
        MyBrowseView()
    }
    .customizationID("com.myApp.browse")
    .defaultVisibility(.hidden, for: .sidebar)
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```

