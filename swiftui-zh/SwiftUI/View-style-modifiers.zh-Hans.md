---
来源： https://developer.apple.com/documentation/SwiftUI/View-style-modifiers
抓取时间： 2025-12-02T17:22:13Z
---

# 样式修改器

**API 集合**

将内置样式应用于不同类型的视图。

## 概览

SwiftUI 为某些类型的视图定义了内置样式，并为特定的显示上下文选择合适的样式。例如，[Label](Label.zh-Hans.md) 可能以图标、字符串标题或两者的形式出现，具体取决于平台、视图是否出现在工具栏中等因素。

您可以使用其中一种样式修改器来覆盖自动样式。这些修改器通常会在容器视图中传播，所以你可以用样式修改器包装整个视图层次结构，以影响层次结构中给定类型的所有视图。某些视图类型可让您创建自定义样式，您也可以使用样式修改器应用这些样式。

有关视图样式的更多信息，请参阅[View-styles](View-styles.zh-Hans.md)。

## 控制

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。
- **datePickerStyle(_:)**：为该视图中的日期选择器设置样式。
- **menuStyle(_:)**：为该视图中的菜单设置样式。
- **pickerStyle(_:)**：为该视图中的拾取器设置样式。
- **toggleStyle(_:)**：设置视图层次结构中切换器的样式。

### 指示器

- **gaugeStyle(_:)**：为该视图中的仪表设置样式。
- **progressViewStyle(_:)**：为该视图中的进度视图设置样式。

### 文本

- **labelStyle(_:)**：设置此视图中标签的样式。
- **textFieldStyle(_:)**：为该视图中的标签设置样式：设置此视图中文本字段的样式。
- **textEditorStyle(_:)**：设置该视图中文本字段的样式：设置此视图中文本编辑器的样式。

## 收藏

- **listStyle(_:)**：为该视图中的列表设置样式。
- **tableStyle(_:)**：为该视图中的表格设置样式。
- **disclosureGroupStyle(_:)**：为该视图中的披露组设置样式。

### 演示

- **navigationSplitViewStyle(_:)**：设置该视图中导航分割视图的样式。
- **tabViewStyle(_:)**：为当前环境中的选项卡视图设置样式。
- **presentedWindowStyle(_:)**：设置通过与此视图交互而创建的窗口的样式。
- **presentedWindowToolbarStyle(_:)**：设置与此视图交互创建的窗口中工具栏的样式。

## 组

- **controlGroupStyle(_:)**：设置此视图中控制组的样式。
- **groupBoxStyle(_:)**：为该视图中的组框设置样式。
- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。

## 绘制视图

- **布局修改器**：通过调整视图的大小、位置、对齐方式、填充等，告诉视图如何在视图层次结构中排列。
- 图形和渲染修改器**：影响系统绘制视图的方式，例如缩放或屏蔽视图，或应用图形效果。


---
source: https://developer.apple.com/documentation/SwiftUI/View-style-modifiers
crawled: 2025-12-02T17:22:13Z
---

# Style modifiers

**API Collection**

Apply built-in styles to different types of views.

## Overview

SwiftUI defines built-in styles for certain kinds of views, and chooses the appropriate style for a particular presentation context. For example, a [Label](Label.zh-Hans.md) might appear as an icon, a string title, or both, depending on factors like the platform, whether the view appears in a toolbar, and so on.

You can override the automatic style by using one of the style modifiers. These modifiers typically propagate through container views, so you can wrap an entire view hierarchy in a style modifier to affect all the views of the given type within the hierarchy. Some view types enable you to create custom styles, which you also apply using style modifiers.

For more information about styling views, see [View-styles](View-styles.zh-Hans.md).

## Controls

- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **datePickerStyle(_:)**: Sets the style for date pickers within this view.
- **menuStyle(_:)**: Sets the style for menus within this view.
- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.

## Indicators

- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.

## Text

- **labelStyle(_:)**: Sets the style for labels within this view.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **textEditorStyle(_:)**: Sets the style for text editors within this view.

## Collections

- **listStyle(_:)**: Sets the style for lists within this view.
- **tableStyle(_:)**: Sets the style for tables within this view.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.

## Presentation

- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.
- **presentedWindowStyle(_:)**: Sets the style for windows created by interacting with this view.
- **presentedWindowToolbarStyle(_:)**: Sets the style for the toolbar in windows created by interacting with this view.

## Groups

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.
- **groupBoxStyle(_:)**: Sets the style for group boxes within this view.
- **indexViewStyle(_:)**: Sets the style for the index view within the current environment.

## Drawing views

- **Layout modifiers**: Tell a view how to arrange itself within a view hierarchy by adjusting its size, position, alignment, padding, and so on.
- **Graphics and rendering modifiers**: Affect the way the system draws a view, for example by scaling or masking a view, or by applying graphical effects.

