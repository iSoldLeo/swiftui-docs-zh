---
来源： https://developer.apple.com/documentation/SwiftUI/TabContent/customizationID(_:)
抓取时间：2025-11-30T20:08:47Z
---

# customizationID(_:)

**实例方法**

设置标签页的标识符，以保持其状态。

## 声明

```swift
nonisolated func customizationID(_ id: String) -> some TabContent<Self.TabValue>

```

## 参数

- **id**：要与选项卡或部分关联的标识符。

## 讨论

标识符必须稳定，包括在应用程序版本更新时。

只有[sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md)样式支持自定义。要启用自定义功能，请使用 [TabViewCustomization](../TabViewCustomization.zh-Hans.md) 将 [TabView](../TabView.zh-Hans.md) 附加到 [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md) 上。

所有支持自定义的标签页和标签页部分都必须有一个自定义 ID。您可以使用[customizationBehavior(_:for:)](customizationBehavior___for.zh-Hans.md) 在所有可调整的选项卡栏位置中指定[disabled](../TabCustomizationBehavior/disabled.zh-Hans.md) 行为，将选项卡标记为不可定制。

如果将自定义 ID 应用于[TabSection](../TabSection.zh-Hans.md)，请确保为该部分中的所有选项卡指定自定义 ID，除非该选项卡已标记为自定义关闭。

下面的示例为所有选项卡和选项卡部分添加了自定义标识符。

```swift
@AppStorage("MyAppTabViewCustomization")
private var customization: TabViewCustomization

TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    .customizationID("com.myApp.home")

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }
    .customizationID("com.myApp.bell")

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
    .customizationID("com.myApp.categories")
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/customizationID(_:)
crawled: 2025-11-30T20:08:47Z
---

# customizationID(_:)

**Instance Method**

Sets the identifier for a tab to persist its state.

## Declaration

```swift
nonisolated func customizationID(_ id: String) -> some TabContent<Self.TabValue>

```

## Parameters

- **id**: The identifier to associate with a tab or section.

## Discussion

The identifier needs to be stable, including across app version updates.

Only the [sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md) style supports supports customization. To enable customization, attach a [TabViewCustomization](../TabViewCustomization.zh-Hans.md) to the [TabView](../TabView.zh-Hans.md) using [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md).

All tabs and tab sections that support customization are required to have a customization ID. You can mark a tab as being non-customizable by specifying a [disabled](../TabCustomizationBehavior/disabled.zh-Hans.md) behavior in all adaptable tab bar placements using [customizationBehavior(_:for:)](customizationBehavior___for.zh-Hans.md).

If you apply a customization ID to a [TabSection](../TabSection.zh-Hans.md), ensure you specify customization IDs for all of the tabs within the section, unless the tab has been marked as having customization turned off.

The following example adds customization identifiers to all tabs and tab sections.

```swift
@AppStorage("MyAppTabViewCustomization")
private var customization: TabViewCustomization

TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    .customizationID("com.myApp.home")

    Tab("Alerts", systemImage: "bell") {
        AlertsView()
    }
    .customizationID("com.myApp.bell")

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
    .customizationID("com.myApp.categories")
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```

