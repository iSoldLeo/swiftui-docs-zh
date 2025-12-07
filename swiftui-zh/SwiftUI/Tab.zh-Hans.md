--- 来源：https://developer.apple.com/documentation/SwiftUI/Tab
抓取时间：2025-12-02T16:23:30Z

---

# Tab

**Structure**

标签页的内容以及标签页视图中与该标签页关联的标签项。

## 声明

```swift
struct Tab<Value, Content, Label>
```

## 创建标签页

- **init(content:)**：创建一个可在标签页视图中使用的新标签页，标签为空。

- **init(value:content:)**：创建一个可在标签页视图中使用的新标签页，标签为空。

- **init(role:content:)**：创建一个可在标签页视图中使用的新标签页，标签为空。

- **init(value:role:content:)**：创建一个新标签页，标签内容根据角色推断得出。

## 创建带标签的标签页

- **init(content:label:)**：创建一个新标签页，标签内容可在标签页视图中使用。

- **init(value:content:label:)**：创建一个新标签页，标签内容可在标签页视图中使用。

- **init(role:content:label:)**：创建一个新标签页，标签内容可在标签页视图中使用。

- **init(value:role:content:label:)**：创建一个新标签页，标签内容可在标签页视图中使用。

## 创建带系统符号的标签页

- **init(_:systemImage:content:)**：创建一个新标签页，标签页项的图像使用系统图像，标签使用本地化字符串。该标签页可在标签页视图中使用。

- **init(_:systemImage:value:content:)**：创建一个选项卡，当选项卡视图的选择与选项卡的值匹配时，选项卡视图会显示该选项卡。选项卡项图像使用系统图像，键标签使用本地化字符串。

- **init(_:systemImage:role:content:)**：创建一个新选项卡，您可以在选项卡视图中使用该选项卡。选项卡项图像使用系统图像，键标签使用本地化字符串。

- **init(_:systemImage:value:role:content:)**：创建一个选项卡，当选项卡视图的选择与选项卡的值匹配时，选项卡视图会显示该选项卡。选项卡项图像使用系统图像，键标签使用本地化字符串。

## 创建带图像的选项卡

- **init(_:image:content:)**：创建一个新选项卡，您可以在选项卡视图中使用该选项卡。键标签使用本地化字符串。

- **init(_:image:value:content:)**：创建一个选项卡，当选项卡视图的选择与选项卡的值匹配时，选项卡视图将显示该选项卡，并带有本地化的字符串键标签。

- **init(_:image:role:content:)**：创建一个新选项卡，您可以在选项卡视图中使用它，并带有本地化的字符串键标签。

- **init(_:image:value:role:content:)**：创建一个选项卡，当选项卡视图的选择与选项卡的值匹配时，选项卡视图将显示该选项卡，并带有本地化的字符串键标签。

## 支持的类型

- **DefaultTabLabel**：选项卡或选项卡部分的默认标签。

## 在选项卡中呈现视图

- **使用选项卡导航增强应用内容**：将应用内容置于中心位置，同时使用选项卡栏快速访问导航。

- **TabView**：使用交互式用户界面元素在多个子视图之间切换的视图。

- **TabRole**：定义选项卡用途的值。

- **TabSection**：可用于在选项卡视图中添加层级结构的容器。

- **tabViewStyle(_:)**：设置当前环境中选项卡视图的样式。

## 符合以下规范

- Copyable

- TabContent


---
source: https://developer.apple.com/documentation/SwiftUI/Tab
crawled: 2025-12-02T16:23:30Z
---

# Tab

**Structure**

The content for a tab and the tab’s associated tab item in a tab view.

## Declaration

```swift
struct Tab<Value, Content, Label>
```

## Creating a tab

- **init(content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(value:content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(role:content:)**: Creates a new tab that you can use in a tab view, with an empty label.
- **init(value:role:content:)**: Creates a new tab with a label inferred from the role.

## Creating a tab with label

- **init(content:label:)**: Creates a new tab with a label that you can use in a tab view.
- **init(value:content:label:)**: Creates a new tab with a label that you can use in a tab view.
- **init(role:content:label:)**: Creates a new tab with a label that you can use in a tab view.
- **init(value:role:content:label:)**: Creates a new tab with a label that you can use in a tab view.

## Creating a tab with system symbol

- **init(_:systemImage:content:)**: Creates a new tab that you can use in a tab view using a system image for the tab item’s image, and a localized string key label.
- **init(_:systemImage:value:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value using a system image for the tab’s tab item image, with a localized string key label.
- **init(_:systemImage:role:content:)**: Creates a new tab that you can use in a tab view using a system image for the tab item’s image, and a localized string key label.
- **init(_:systemImage:value:role:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value using a system image for the tab’s tab item image, with a localized string key label.

## Creating a tab with image

- **init(_:image:content:)**: Creates a new tab that you can use in a tab view, with a localized string key label.
- **init(_:image:value:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value, with a localized string key label.
- **init(_:image:role:content:)**: Creates a new tab that you can use in a tab view, with a localized string key label.
- **init(_:image:value:role:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value, with a localized string key label.

## Supporting types

- **DefaultTabLabel**: The default label to use for a tab or tab section.

## Presenting views in tabs

- **Enhancing your app’s content with tab navigation**: Keep your app content front and center while providing quick access to navigation using the tab bar.
- **TabView**: A view that switches between multiple child views using interactive user interface elements.
- **TabRole**: A value that defines the purpose of the tab.
- **TabSection**: A container that you can use to add hierarchy within a tab view.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.

## Conforms To

- Copyable
- TabContent

