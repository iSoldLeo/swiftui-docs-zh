---
来源：https://developer.apple.com/documentation/SwiftUI/TabContent/customizationBehavior(_:for:)
抓取时间：2025-12-03T06:01:48Z
---

# customizationBehavior(_:for:)

**实例方法**

配置自定义选项卡视图内容的自定义行为。

## 声明

```swift
nonisolated func customizationBehavior(_ behavior: TabCustomizationBehavior, for placements: AdaptableTabBarPlacement...) -> some TabContent<Self.TabValue>

```

## 参数

- **behavior**：自定义选项卡内容的自定义行为。

## 讨论

[sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md)样式支持自定义 iPad 上的标签栏和侧边栏。要启用自定义功能，请使用[tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md)将[TabViewCustomization](../TabViewCustomization.zh-Hans.md)附加到[TabView](../TabView.zh-Hans.md)。

此修改器对其他平台或不支持自定义的[TabViewStyle](../TabViewStyle.zh-Hans.md) 无效。

使用此修改器可指定一个人可对指定位置的项目执行的自定义行为。要启用自定义，所有选项卡都需要一个自定义 ID。

在下面的示例中，侧边栏和标签栏中的标签支持所有不同类型的自定义。

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

通过向该修改器传递[disabled](../TabCustomizationBehavior/disabled.zh-Hans.md)值，可以创建一个无法隐藏或移动的项目。只关闭重要标签页的自定义功能，因为人们需要这些标签页来使用应用程序的常用功能。如果您同时关闭了侧边栏和标签栏的自定义功能，那么就不需要自定义 ID 了。

```swift
@AppStorage("MyAppTabViewCustomization")
private var customization: TabViewCustomization

TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    .customizationBehavior(.disabled, for: .sidebar, .tabBar)

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

传递[reorderable](../TabCustomizationBehavior/reorderable.zh-Hans.md)的值可创建一个人们可以移动但不能隐藏的项目。在 [sidebar](../AdaptableTabBarPlacement/sidebar.zh-Hans.md)中，人们只能对部分内的选项卡重新排序。

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
    .customizationBehavior(.reorderable, for: .sidebar)
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```

您可以单独定制每个位置的行为。下面的示例允许对侧边栏中的子标签重新排序，但禁止隐藏或移动标签栏中的标签。

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
    .customizationBehavior(.reorderable, for: .sidebar)
    .customizationBehavior(.disabled, for: .tabBar)
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```


---
source: https://developer.apple.com/documentation/SwiftUI/TabContent/customizationBehavior(_:for:)
crawled: 2025-12-03T06:01:48Z
---

# customizationBehavior(_:for:)

**Instance Method**

Configures the customization behavior of customizable tab view content.

## Declaration

```swift
nonisolated func customizationBehavior(_ behavior: TabCustomizationBehavior, for placements: AdaptableTabBarPlacement...) -> some TabContent<Self.TabValue>

```

## Parameters

- **behavior**: The customization behavior of the customizable tab content.

## Discussion

The [sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md) style supports customization of the tab bar and sidebar on iPad. To enable customization, attach a [TabViewCustomization](../TabViewCustomization.zh-Hans.md) to the [TabView](../TabView.zh-Hans.md) using [tabViewCustomization(_:)](../View/tabViewCustomization.zh-Hans.md).

This modifier has no effect on other platforms or on a [TabViewStyle](../TabViewStyle.zh-Hans.md) that doesn’t support customization.

Use this modifier to specify the customization behavior a person can perform on items in the specified placement. To enable customization, all tabs need a customization ID.

In the following example, the tabs support all of the different kinds of customizations in both the sidebar and tab bar.

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

You can create an item that cannot be hidden or moved by passing a value of [disabled](../TabCustomizationBehavior/disabled.zh-Hans.md) to this modifier. Only turn off customization for important tabs that people need for the app to do common functionality. If you turn off customization for both the sidebar and tab bar, then a customization ID isn’t necessary.

```swift
@AppStorage("MyAppTabViewCustomization")
private var customization: TabViewCustomization

TabView {
    Tab("Home", systemImage: "house") {
        HomeView()
    }
    .customizationBehavior(.disabled, for: .sidebar, .tabBar)

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

Pass a value of [reorderable](../TabCustomizationBehavior/reorderable.zh-Hans.md) to create an item that people can move, but can’t hide. In the [sidebar](../AdaptableTabBarPlacement/sidebar.zh-Hans.md), people can only reorder tabs within sections.

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
    .customizationBehavior(.reorderable, for: .sidebar)
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```

You can individually customize each placement’s behavior. The following example would allow reordering of children in the sidebar but prohibit hiding or moving the tab in the tab bar.

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
    .customizationBehavior(.reorderable, for: .sidebar)
    .customizationBehavior(.disabled, for: .tabBar)
}
.tabViewStyle(.sidebarAdaptable)
.tabViewCustomization($customization)
```

