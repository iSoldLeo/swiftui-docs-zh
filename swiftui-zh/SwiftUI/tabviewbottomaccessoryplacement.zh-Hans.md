---
来源： https://developer.apple.com/documentation/swiftui/tabviewbottomaccessoryplacement
抓取时间： 2025-12-03T06:00:02Z
---

# TabViewBottomAccessoryPlacement

**Enumeration**

标签视图中底部附件的位置。您可以使用它根据位置调整附件视图的内容。

## 声明

```swift
enum TabViewBottomAccessoryPlacement
```

## 概览

下面的示例显示了内嵌视图时的播放控件，以及展开视图时的扩展滑块播放器视图。

```swift
struct MusicPlaybackView: View {
    @Environment(\.tabViewBottomAccessoryPlacement) var placement

    var body: some View {
        switch placement {
        case .inline:
            ControlsPlaybackView()
        case .expanded:
            SliderPlaybackView()
    }
}
```

您可以使用[tabViewBottomAccessory(content:)](View/tabViewBottomAccessory_content.zh-Hans.md)设置`TabView`底部附件。

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
.tabViewBottomAccessory {
    HomeStatusView()
}
```

## 枚举案例

- **TabViewBottomAccessoryPlacement.expanded**：如果有底部选项卡栏，该栏在底部选项卡栏顶部展开，或在选项卡内容视图的底部展开。
- **TabViewBottomAccessoryPlacement.inline**：视图显示与底部标签栏一致。

## 配置标签栏

- **defaultAdaptableTabBarPlacement(_:)**：使用自适应侧边栏样式指定选项卡视图中选项卡的默认位置。
- **tabViewSidebarHeader(content:)**：在选项卡视图的侧边栏中添加自定义页眉。
- **tabViewSidebarFooter(content:)**：在选项卡视图的边栏中添加自定义页脚。
- **tabViewSidebarBottomBar(content:)**：在选项卡视图的边栏中添加自定义底栏。
- **AdaptableTabBarPlacement**：使用自适应侧边栏样式在选项卡视图中放置选项卡。
- **tabBarPlacement**：标签栏的当前位置。
- **TabBarPlacement**：选项卡视图中选项卡的位置。
- **isTabBarShowingSections**：布尔值，用于确定选项卡视图是否显示选项卡部分的展开内容。
- **TabBarMinimizeBehavior**：一个布尔值，用于确定选项卡视图是否显示选项卡部分的展开内容。

## 符合

- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/tabviewbottomaccessoryplacement
crawled: 2025-12-03T06:00:02Z
---

# TabViewBottomAccessoryPlacement

**Enumeration**

A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

## Declaration

```swift
enum TabViewBottomAccessoryPlacement
```

## Overview

The following example shows playback controls when the view is inline, and an expanded slider player view when the view is expanded.

```swift
struct MusicPlaybackView: View {
    @Environment(\.tabViewBottomAccessoryPlacement) var placement

    var body: some View {
        switch placement {
        case .inline:
            ControlsPlaybackView()
        case .expanded:
            SliderPlaybackView()
    }
}
```

You can set the `TabView` bottom accessory using [tabViewBottomAccessory(content:)](View/tabViewBottomAccessory_content.zh-Hans.md)

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
.tabViewBottomAccessory {
    HomeStatusView()
}
```

## Enumeration Cases

- **TabViewBottomAccessoryPlacement.expanded**: The bar is expanded on top of the bottom tab bar, if there is a bottom tab bar, or at the bottom of the tab’s content view.
- **TabViewBottomAccessoryPlacement.inline**: The view is displayed in line with the bottom tab bar.

## Configuring a tab bar

- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **AdaptableTabBarPlacement**: A placement for tabs in a tab view using the adaptable sidebar style.
- **tabBarPlacement**: The current placement of the tab bar.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

