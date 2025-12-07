--- 来源：https://developer.apple.com/documentation/swiftui/view/tabviewcustomization(_:)

抓取时间：2025-12-02T16:16:27Z

---

# tabViewCustomization(_:)

**实例方法**

指定要应用于标签视图侧边栏表示的自定义设置。

## 声明

```swift
nonisolated func tabViewCustomization(_ customization: Binding<TabViewCustomization>?) -> some View

```

## 参数

- **customization**：用于存储用户自定义设置的自定义对象。

## 说明

只有 [sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md) 样式支持自定义。使用此修饰符指定非空的 [TabViewCustomization](../TabViewCustomization.zh-Hans.md) 对象即可启用自定义。

默认情况下，如果用户未进行任何自定义设置，标签页将按照默认的构建器可见性显示，而各个部分则按照您在标签页视图的标签页构建器中声明的顺序显示。

您可以使用 [defaultVisibility(_:for:)](../TabContent/defaultVisibility___for.zh-Hans.md) 和 [sidebar](../AdaptableTabBarPlacement/sidebar.zh-Hans.md) 位置来更改默认可见性。

您可以通过在构建器中更改顺序来更改默认的部分顺序。如果存在已保存的自定义设置，则在更改顺序时，请调用 [resetTabOrder()](../TabViewCustomization/SectionCustomization/resetTabOrder.zh-Hans.md) 来重置顺序。

所有支持自定义的标签页和标签页部分都需要一个自定义 ID。您可以通过在所有可调整的标签栏位置中使用 [customizationBehavior(_:for:)](../TabContent/customizationBehavior___for.zh-Hans.md) 指定 [disabled](../TabCustomizationBehavior/disabled.zh-Hans.md) 行为，将标签页标记为不可自定义。

在 macOS 上，系统提供了重新排序部分的默认交互方式，但没有提供控制单个标签页可见性的默认交互方式。如果需要自定义体验，可以通过设置自定义选项卡的可见性来实现。

以下代码示例使用 `@AppStorage` 自动保存用户所做的任何可见性或分区顺序自定义设置。

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

## 启用选项卡自定义

- **TabViewCustomization**：用户对可自适应侧边栏选项卡视图所做的自定义设置。

- **TabCustomizationBehavior**：可自定义选项卡视图内容的自定义行为。


---
source: https://developer.apple.com/documentation/swiftui/view/tabviewcustomization(_:)
crawled: 2025-12-02T16:16:27Z
---

# tabViewCustomization(_:)

**Instance Method**

Specifies the customizations to apply to the sidebar representation of the tab view.

## Declaration

```swift
nonisolated func tabViewCustomization(_ customization: Binding<TabViewCustomization>?) -> some View

```

## Parameters

- **customization**: The customization object to store user customization in.

## Discussion

Only the [sidebarAdaptable](../TabViewStyle/sidebarAdaptable.zh-Hans.md) style supports supports customization. Specifying a non-nil [TabViewCustomization](../TabViewCustomization.zh-Hans.md) object using this modifier enables customization.

By default, if a person hasn’t made customizations, tabs appear according to the default builder visibilities and sections appear in the order you declare in the tab view’s tab builder.

You can change the default visibility by using the [defaultVisibility(_:for:)](../TabContent/defaultVisibility___for.zh-Hans.md) with a [sidebar](../AdaptableTabBarPlacement/sidebar.zh-Hans.md) placement.

You can change the default section order by changing the order in the builder. If there’s an existing persisted customization, reset the order by calling [resetTabOrder()](../TabViewCustomization/SectionCustomization/resetTabOrder.zh-Hans.md) when you change the order.

All tabs and tab sections that support customization need to have a customization ID. You can mark a tab as being non-customizable by specifying a [disabled](../TabCustomizationBehavior/disabled.zh-Hans.md) behavior in all adaptable tab bar placements using [customizationBehavior(_:for:)](../TabContent/customizationBehavior___for.zh-Hans.md).

On macOS, a default interaction is provided for reordering sections but not for controlling the visibility of individual tabs. A custom experience should be provided if desired by setting the visibility of the tab on the customization.

The following code example uses `@AppStorage` to automatically persist any visibility or section order customizations a person makes.

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

## Enabling tab customization

- **TabViewCustomization**: The customizations a person makes to an adaptable sidebar tab view.
- **TabCustomizationBehavior**: The customization behavior of customizable tab view content.

