--- 来源：https://developer.apple.com/documentation/SwiftUI/TabSection
抓取时间：2025-12-02T16:23:32Z

---

# TabSection

**Structure**

一个可用于在标签视图中添加层级结构的容器。

## 声明

```swift
struct TabSection<Header, Content, Footer, SelectionValue>
```

## 概述

使用 [TabSection](TabSection.zh-Hans.md) 将标签内容组织成不同的部分。每个部分都包含您为每个实例提供的自定义标签内容。您还可以为每个部分提供标题。

## 创建标签部分

- **init(content:)**：使用提供的部分内容创建一个部分。

- **init(_:content:)**：使用提供的内容创建一个部分。

- **init(content:header:)**：创建一个包含标题和指定内容的分区。

## 支持的类型

- **DefaultTabLabel**：用于选项卡或选项卡分区的默认标签。

## 以选项卡形式呈现视图

- **使用选项卡导航增强应用内容**：将应用内容置于中心位置，同时使用选项卡栏快速访问导航。

- **TabView**：使用交互式用户界面元素在多个子视图之间切换的视图。

- **Tab**：选项卡视图中选项卡的内容及其关联的选项卡项。

- **TabRole**：定义选项卡用途的值。

- **tabViewStyle(_:)**：设置当前环境中选项卡视图的样式。

## 符合以下规范

- 可复制

- TabContent


---
source: https://developer.apple.com/documentation/SwiftUI/TabSection
crawled: 2025-12-02T16:23:32Z
---

# TabSection

**Structure**

A container that you can use to add hierarchy within a tab view.

## Declaration

```swift
struct TabSection<Header, Content, Footer, SelectionValue>
```

## Overview

Use [TabSection](TabSection.zh-Hans.md) to organize tab content into separate sections. Each section has custom tab content that you provide on a per-instance basis. You can also provide a header for each section.

## Creating a tab section

- **init(content:)**: Creates a section with the provided section content.
- **init(_:content:)**: Creates a section with the provided content.
- **init(content:header:)**: Creates a section with a header and the provided section content.

## Supporting types

- **DefaultTabLabel**: The default label to use for a tab or tab section.

## Presenting views in tabs

- **Enhancing your app’s content with tab navigation**: Keep your app content front and center while providing quick access to navigation using the tab bar.
- **TabView**: A view that switches between multiple child views using interactive user interface elements.
- **Tab**: The content for a tab and the tab’s associated tab item in a tab view.
- **TabRole**: A value that defines the purpose of the tab.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.

## Conforms To

- Copyable
- TabContent

