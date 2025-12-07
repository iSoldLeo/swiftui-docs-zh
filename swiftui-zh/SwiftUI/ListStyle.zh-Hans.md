--- 来源：https://developer.apple.com/documentation/SwiftUI/ListStyle

抓取时间：2025-12-02T17:33:22Z

---

# ListStyle

**Protocol**

描述列表行为和外观的协议。

## 声明

```swift
protocol ListStyle
```

## 获取内置列表样式

- **automatic**：描述平台默认列表行为和外观的列表样式。

- **bordered**：描述标准边框列表行为和外观的列表样式。

- **carousel**：轮播列表样式。

- **elliptical**：描述椭圆形列表行为和外观的列表样式。

- **grouped**：描述分组列表的行为和外观的列表样式。

- **inset**：描述嵌入式列表的行为和外观的列表样式。

- **insetGrouped**：描述嵌入式分组列表的行为和外观的列表样式。

- **plain**：描述普通列表的行为和外观的列表样式。

- **sidebar**：描述侧边栏列表的行为和外观的列表样式。

## 已弃用样式

- **bordered(alternatesRowBackgrounds:)**：描述带有标准边框的列表的行为和外观的列表样式。

- **inset(alternatesRowBackgrounds:)**：描述带有可选交替行背景的嵌入式列表的行为和外观的列表样式。

## 支持的类型

- **DefaultListStyle**：描述平台默认列表行为和外观的列表样式。

- **BorderedListStyle**：描述带有标准边框的列表的行为和外观的列表样式。

- **CarouselListStyle**：轮播列表样式。

- **EllipticalListStyle**：描述椭圆列表的行为和外观的列表样式。

- **GroupedListStyle**：描述分组列表的行为和外观的列表样式。

- **InsetListStyle**：描述内嵌列表的行为和外观的列表样式。

- **InsetGroupedListStyle**：描述内嵌分组列表的行为和外观的列表样式。

- **PlainListStyle**：描述普通列表的行为和外观的列表样式。

- **SidebarListStyle**：描述侧边栏列表的行为和外观的列表样式。

## 设置集合视图样式

- **listStyle(_:)**：设置此视图中列表的样式。

- **tableStyle(_:)**：设置此视图中表格的样式。

- **TableStyle**：一种将自定义外观应用于视图中所有表格的类型。

- **TableStyleConfiguration**：表格的属性。

- **disclosureGroupStyle(_:)**：设置此视图中披露组的样式。

- **DisclosureGroupStyle**：一种指定视图层次结构中披露组的外观和交互方式的类型。

## 符合规范的类型

- BorderedListStyle

- CarouselListStyle

- DefaultListStyle

- EllipticalListStyle

- GroupedListStyle

- InsetGroupedListStyle

- InsetListStyle

- PlainListStyle

- SidebarListStyle


---
source: https://developer.apple.com/documentation/SwiftUI/ListStyle
crawled: 2025-12-02T17:33:22Z
---

# ListStyle

**Protocol**

A protocol that describes the behavior and appearance of a list.

## Declaration

```swift
protocol ListStyle
```

## Getting built-in list styles

- **automatic**: The list style that describes a platform’s default behavior and appearance for a list.
- **bordered**: The list style that describes the behavior and appearance of a list with standard border.
- **carousel**: The carousel list style.
- **elliptical**: The list style that describes the behavior and appearance of an elliptical list.
- **grouped**: The list style that describes the behavior and appearance of a grouped list.
- **inset**: The list style that describes the behavior and appearance of an inset list.
- **insetGrouped**: The list style that describes the behavior and appearance of an inset grouped list.
- **plain**: The list style that describes the behavior and appearance of a plain list.
- **sidebar**: The list style that describes the behavior and appearance of a sidebar list.

## Deprecated styles

- **bordered(alternatesRowBackgrounds:)**: The list style that describes the behavior and appearance of a list with standard border.
- **inset(alternatesRowBackgrounds:)**: The list style that describes the behavior and appearance of an inset list with optional alternating row backgrounds.

## Supporting types

- **DefaultListStyle**: The list style that describes a platform’s default behavior and appearance for a list.
- **BorderedListStyle**: The list style that describes the behavior and appearance of a list with standard border.
- **CarouselListStyle**: The carousel list style.
- **EllipticalListStyle**: The list style that describes the behavior and appearance of an elliptical list.
- **GroupedListStyle**: The list style that describes the behavior and appearance of a grouped list.
- **InsetListStyle**: The list style that describes the behavior and appearance of an inset list.
- **InsetGroupedListStyle**: The list style that describes the behavior and appearance of an inset grouped list.
- **PlainListStyle**: The list style that describes the behavior and appearance of a plain list.
- **SidebarListStyle**: The list style that describes the behavior and appearance of a sidebar list.

## Styling collection views

- **listStyle(_:)**: Sets the style for lists within this view.
- **tableStyle(_:)**: Sets the style for tables within this view.
- **TableStyle**: A type that applies a custom appearance to all tables within a view.
- **TableStyleConfiguration**: The properties of a table.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.
- **DisclosureGroupStyle**: A type that specifies the appearance and interaction of disclosure groups within a view hierarchy.

## Conforming Types

- BorderedListStyle
- CarouselListStyle
- DefaultListStyle
- EllipticalListStyle
- GroupedListStyle
- InsetGroupedListStyle
- InsetListStyle
- PlainListStyle
- SidebarListStyle

