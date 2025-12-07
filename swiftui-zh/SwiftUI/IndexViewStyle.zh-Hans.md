--- 来源：https://developer.apple.com/documentation/SwiftUI/IndexViewStyle
抓取时间：2025-12-02T17:33:36Z

---

# IndexViewStyle

**Protocol**

定义视图层级结构中所有 `IndexView` 实例的实现。

## 声明

```swift
protocol IndexViewStyle
```

## 概述

要配置视图层级结构的当前 `IndexViewStyle`，请使用 `.indexViewStyle()` 修饰符。

## 获取内置索引视图样式

- **page**：一种索引视图样式，用于在其内容上方放置页面索引视图。

- **page(backgroundDisplayMode:)**：一种索引视图样式，用于在页面内容上方添加页面索引视图。

## 支持的类型

- **PageIndexViewStyle**：一种索引视图样式，用于在页面内容上方添加页面索引视图。

## 样式组

- **controlGroupStyle(_:)**：设置此视图中控件组的样式。

- **ControlGroupStyle**：定义视图层次结构中所有控件组的实现。

- **ControlGroupStyleConfiguration**：控件组的属性。

- **formStyle(_:)**：设置视图层次结构中表单的样式。

- **FormStyle**：表单的外观和行为。

- **FormStyleConfiguration**：表单实例的属性。

- **groupBoxStyle(_:)**：设置此视图中分组框的样式。

- **GroupBoxStyle**：指定视图层次结构中所有分组框的外观和交互方式的类型。

- **GroupBoxStyleConfiguration**：分组框实例的属性。

- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。

- **labeledContentStyle(_:)**：设置带标签内容的样式。

- **LabeledContentStyle**：带标签内容实例的外观和行为。

- **LabeledContentStyleConfiguration**：带标签内容实例的属性。

## 符合规范的类型

- PageIndexViewStyle


---
source: https://developer.apple.com/documentation/SwiftUI/IndexViewStyle
crawled: 2025-12-02T17:33:36Z
---

# IndexViewStyle

**Protocol**

Defines the implementation of all `IndexView` instances within a view hierarchy.

## Declaration

```swift
protocol IndexViewStyle
```

## Overview

To configure the current `IndexViewStyle` for a view hierarchy, use the `.indexViewStyle()` modifier.

## Getting built-in index view styles

- **page**: An index view style that places a page index view over its content.
- **page(backgroundDisplayMode:)**: An index view style that places a page index view over its content.

## Supporting types

- **PageIndexViewStyle**: An index view style that places a page index view over its content.

## Styling groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
- **ControlGroupStyle**: Defines the implementation of all control groups within a view hierarchy.
- **ControlGroupStyleConfiguration**: The properties of a control group.
- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **FormStyle**: The appearance and behavior of a form.
- **FormStyleConfiguration**: The properties of a form instance.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.
- **GroupBoxStyle**: A type that specifies the appearance and interaction of all group boxes within a view hierarchy.
- **GroupBoxStyleConfiguration**: The properties of a group box instance.
- **indexViewStyle(_:)**: Sets the style for the index view within the current environment.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **LabeledContentStyle**: The appearance and behavior of a labeled content instance..
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

## Conforming Types

- PageIndexViewStyle

