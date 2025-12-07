---
来源： https://developer.apple.com/documentation/swiftui/environmentvalues/tabbarplacement
抓取时间： 2025-12-03T05:59:58Z
---

# tabBarPlacement

**实例属性**

标签栏的当前位置。

## 声明

```swift
var tabBarPlacement: TabBarPlacement? { get }
```

## 讨论

请注意，该值只在[TabView](../TabView.zh-Hans.md) 的内容视图中设置。

`nil`值对应于未定义的位置。

## 配置标签栏

- **defaultAdaptableTabBarPlacement(_:)**：使用自适应侧边栏样式指定选项卡视图中选项卡的默认位置。
- **tabViewSidebarHeader(content:)**：在选项卡视图的侧边栏中添加自定义页眉。
- **tabViewSidebarFooter(content:)**：在选项卡视图的边栏中添加自定义页脚。
- **tabViewSidebarBottomBar(content:)**：在选项卡视图的侧边栏中添加自定义底栏。
- **AdaptableTabBarPlacement**：使用自适应侧边栏样式在选项卡视图中放置选项卡。
- **TabBarPlacement**：标签视图中标签的位置。
- **isTabBarShowingSections**：布尔值，用于确定选项卡视图是否显示选项卡部分的展开内容。
- **TabBarMinimizeBehavior**：一个布尔值，用于确定选项卡视图是否显示已展开的选项卡部分内容。
- **TabViewBottomAccessoryPlacement**：标签视图中底部附件的位置。您可以使用它根据位置调整附件视图的内容。


---
source: https://developer.apple.com/documentation/swiftui/environmentvalues/tabbarplacement
crawled: 2025-12-03T05:59:58Z
---

# tabBarPlacement

**Instance Property**

The current placement of the tab bar.

## Declaration

```swift
var tabBarPlacement: TabBarPlacement? { get }
```

## Discussion

Note that this value is only set within the content views of a [TabView](../TabView.zh-Hans.md).

A `nil` value corresponds to an undefined placement.

## Configuring a tab bar

- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **AdaptableTabBarPlacement**: A placement for tabs in a tab view using the adaptable sidebar style.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**
- **TabViewBottomAccessoryPlacement**: A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

