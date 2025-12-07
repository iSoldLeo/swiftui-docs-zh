---
来源： https://developer.apple.com/documentation/swiftui/tabbarplacement
抓取时间： 2025-12-03T05:59:59Z
---

# TabBarPlacement

**Structure**

标签视图中标签的位置。

## 声明

```swift
struct TabBarPlacement
```

## 类型属性

- **bottomBar**：选项卡视图的底部栏。
- **ornament**：作为装饰物显示的选项卡视图。
- **pageIndicator**：选项卡视图显示为指示器，可显示页面内的位置。
- **sidebar**：选项卡视图的侧边栏。
- **topBar**：选项卡视图的顶部栏。

## 配置标签栏

- **defaultAdaptableTabBarPlacement(_:)**：使用自适应侧边栏样式指定选项卡视图中选项卡的默认位置。
- **tabViewSidebarHeader(content:)**：在选项卡视图的侧边栏中添加自定义标题。
- **tabViewSidebarFooter(content:)**：在选项卡视图的边栏中添加自定义页脚。
- **tabViewSidebarBottomBar(content:)**：在选项卡视图的侧边栏中添加自定义底栏。
- **AdaptableTabBarPlacement**：使用自适应侧边栏样式在选项卡视图中放置选项卡。
- **tabBarPlacement**：选项卡栏的当前位置。
- **isTabBarShowingSections**：布尔值，用于确定选项卡视图是否显示选项卡部分的展开内容。
- **TabBarMinimizeBehavior**：一个布尔值，用于确定选项卡视图是否显示已展开的选项卡部分内容。
- **TabViewBottomAccessoryPlacement**：标签视图中底部附件的位置。您可以使用它根据位置调整附件视图的内容。

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/swiftui/tabbarplacement
crawled: 2025-12-03T05:59:59Z
---

# TabBarPlacement

**Structure**

A placement for tabs in a tab view.

## Declaration

```swift
struct TabBarPlacement
```

## Type Properties

- **bottomBar**: Bottom bar of a tab view.
- **ornament**: Tab view displaying as an ornament.
- **pageIndicator**: Tab view displaying as an indicator that shows the position within the pages.
- **sidebar**: The sidebar of a tab view.
- **topBar**: Top bar of a tab view.

## Configuring a tab bar

- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **AdaptableTabBarPlacement**: A placement for tabs in a tab view using the adaptable sidebar style.
- **tabBarPlacement**: The current placement of the tab bar.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**
- **TabViewBottomAccessoryPlacement**: A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

## Conforms To

- Equatable
- Hashable

