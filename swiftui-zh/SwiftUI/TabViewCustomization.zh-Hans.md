---
来源： https://developer.apple.com/documentation/SwiftUI/TabViewCustomization
抓取时间：2025-12-02T17:30:00Z
---

# TabViewCustomization

**Structure**

用户对可调整侧边栏标签视图的自定义。

## 声明

```swift
struct TabViewCustomization
```

## 概览

默认情况下，如果用户没有进行自定义，则选项卡会按照默认的创建器可见性显示，各部分会按照您在选项卡视图的选项卡创建器中声明的顺序显示。

您可以使用[defaultVisibility(_:for:)](TabContent/defaultVisibility___for.zh-Hans.md) 和[sidebar](AdaptableTabBarPlacement/sidebar.zh-Hans.md) 位置来更改默认可见性。

您可以通过在生成器中更改顺序来更改默认的章节顺序。如果已有持久化定制，请在更改顺序时调用 [resetTabOrder()](TabViewCustomization/SectionCustomization/resetTabOrder.zh-Hans.md) 重置顺序。

所有支持自定义的标签页和标签页部分都需要有一个自定义 ID。您可以通过使用[disabled](TabCustomizationBehavior/disabled.zh-Hans.md) 在所有可调整的标签栏位置中指定[customizationBehavior(_:for:)](TabContent/customizationBehavior___for.zh-Hans.md) 行为，将标签页标记为不可定制。

在 macOS 上，默认交互方式可用于重新排序部分，但不能用于控制单个选项卡的可见性。如果需要，可以通过设置自定义选项卡的可见性来提供自定义体验。

下面的代码示例使用 `@AppStorage` 自动坚持用户所做的任何可见性或分区顺序自定义。

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

## 结构

- **TabViewCustomization.SectionCustomization**：用户对[TabSection](TabSection.zh-Hans.md)进行的定制。
- **TabViewCustomization.TabCustomization**：用户对[Tab](Tab.zh-Hans.md) 进行的自定义设置。

## 初始化程序

- **init()**：创建一个空的自定义标签页边栏。

### 实例方法

- **resetSectionOrder()**：将所有部分的排序重置为默认值，保留自定义选项卡的可见性。
- **resetSectionOrder(for:)**：将带有`sectionID` 的部分的排序恢复为默认值，保留任何自定义选项卡的可见性。
- **resetVisibility()**：将所有选项卡侧边栏的可见性重置为默认，保留分区自定义。

### 下标

- **subscript(section:)**：栏目的自定义，由其自定义标识符标识。
- **subscript(sectionID:)**：节的子节的自定义，由节的自定义标识符标识。
- **subscript(sidebarVisibility:)**：标签页的可见性，由其自定义标识符标识。
- **subscript(tab:)**：标签页的自定义，由其自定义标识符标识。

## 启用自定义选项卡

- **tabViewCustomization(_:)**：指定应用于选项卡视图侧边栏表示的自定义。
- **TabCustomizationBehavior**：自定义选项卡视图内容的自定义行为。

## 符合

- 可解码
- 可编码
- 可等价
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/TabViewCustomization
crawled: 2025-12-02T17:30:00Z
---

# TabViewCustomization

**Structure**

The customizations a person makes to an adaptable sidebar tab view.

## Declaration

```swift
struct TabViewCustomization
```

## Overview

By default, if a person hasn’t made customizations, tabs appear according to the default builder visibilities and sections appear in the order you declare in the tab view’s tab builder.

You can change the default visibility by using the [defaultVisibility(_:for:)](TabContent/defaultVisibility___for.zh-Hans.md) with a [sidebar](AdaptableTabBarPlacement/sidebar.zh-Hans.md) placement.

You can change the default section order by changing the order in the builder. If there’s an existing persisted customization, reset the order by calling [resetTabOrder()](TabViewCustomization/SectionCustomization/resetTabOrder.zh-Hans.md) when you change the order.

All tabs and tab sections that support customization need to have a customization ID. You can mark a tab as being non-customizable by specifying a [disabled](TabCustomizationBehavior/disabled.zh-Hans.md) behavior in all adaptable tab bar placements using [customizationBehavior(_:for:)](TabContent/customizationBehavior___for.zh-Hans.md).

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

## Structures

- **TabViewCustomization.SectionCustomization**: The customizations a user has made to a [TabSection](TabSection.zh-Hans.md).
- **TabViewCustomization.TabCustomization**: The customizations a user has made to a [Tab](Tab.zh-Hans.md).

## Initializers

- **init()**: Creates an empty tab sidebar customization.

## Instance Methods

- **resetSectionOrder()**: Resets ordering back to the default for all sections, preserving the customized tab visibilities.
- **resetSectionOrder(for:)**: Resets ordering back to the default for the section with `sectionID`, preserving any customized tab visibilities.
- **resetVisibility()**: Resets all tab sidebar visibilities back to the default, preserving the section customizations.

## Subscripts

- **subscript(section:)**: The customization of the section, identified by its customization identifier.
- **subscript(sectionID:)**: The customization for a section’s children, identified by the section’s customization identifier.
- **subscript(sidebarVisibility:)**: The visibility of the tab identified by its customization identifier.
- **subscript(tab:)**: The customization of the tab, identified by its customization identifier.

## Enabling tab customization

- **tabViewCustomization(_:)**: Specifies the customizations to apply to the sidebar representation of the tab view.
- **TabCustomizationBehavior**: The customization behavior of customizable tab view content.

## Conforms To

- Decodable
- Encodable
- Equatable
- Sendable
- SendableMetatype

