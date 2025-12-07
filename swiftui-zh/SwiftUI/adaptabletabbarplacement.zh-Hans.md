--- 来源：https://developer.apple.com/documentation/swiftui/adaptabletabbarplacement
抓取时间：2025-12-03T05:59:57Z

---

# AdaptableTabBarPlacement

**Structure**

使用自适应侧边栏样式的标签视图中标签的位置。

## 声明

```swift
struct AdaptableTabBarPlacement
```

## 类型属性

- **automatic**：自动位置。

- **sidebar**：标签视图的侧边栏。

- **tabBar**：标签视图的标签栏。

## 配置标签栏

- **defaultAdaptableTabBarPlacement(_:)**：指定使用自适应侧边栏样式的标签视图中标签的默认位置。

- **tabViewSidebarHeader(content:)**：为标签视图的侧边栏添加自定义标题。

- **tabViewSidebarFooter(content:)**：为标签视图的侧边栏添加自定义页脚。

- **tabViewSidebarBottomBar(content:)**：为标签视图的侧边栏添加自定义底部栏。

- **tabBarPlacement**：标签栏的当前位置。

- **TabBarPlacement**：标签视图中标签的位置。

- **isTabBarShowingSections**：一个布尔值，用于确定标签视图是否显示标签部分的展开内容。

- **TabBarMinimizeBehavior**

- **TabViewBottomAccessoryPlacement**：标签视图中底部附件的位置。您可以根据位置调整附件视图的内容。

## 符合以下标准

- Equatable 协议

- Hashable 协议


---
source: https://developer.apple.com/documentation/swiftui/adaptabletabbarplacement
crawled: 2025-12-03T05:59:57Z
---

# AdaptableTabBarPlacement

**Structure**

A placement for tabs in a tab view using the adaptable sidebar style.

## Declaration

```swift
struct AdaptableTabBarPlacement
```

## Type Properties

- **automatic**: The automatic placement.
- **sidebar**: The sidebar of a tab view.
- **tabBar**: The tab bar of a tab view.

## Configuring a tab bar

- **defaultAdaptableTabBarPlacement(_:)**: Specifies the default placement for the tabs in a tab view using the adaptable sidebar style.
- **tabViewSidebarHeader(content:)**: Adds a custom header to the sidebar of a tab view.
- **tabViewSidebarFooter(content:)**: Adds a custom footer to the sidebar of a tab view.
- **tabViewSidebarBottomBar(content:)**: Adds a custom bottom bar to the sidebar of a tab view.
- **tabBarPlacement**: The current placement of the tab bar.
- **TabBarPlacement**: A placement for tabs in a tab view.
- **isTabBarShowingSections**: A Boolean value that determines whether a tab view shows the expanded contents of a tab section.
- **TabBarMinimizeBehavior**
- **TabViewBottomAccessoryPlacement**: A placement of the bottom accessory in a tab view. You can use this to adjust the content of the accessory view based on the placement.

## Conforms To

- Equatable
- Hashable

