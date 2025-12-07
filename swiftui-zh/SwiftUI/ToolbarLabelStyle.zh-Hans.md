--- 来源：https://developer.apple.com/documentation/SwiftUI/ToolbarLabelStyle
抓取时间：2025-12-02T17:31:26Z

---

# ToolbarLabelStyle

**Structure**

工具栏的标签样式。

## 声明

```swift
struct ToolbarLabelStyle
```

## 概述

将此类型与 [windowToolbarLabelStyle(fixed:)](scene/windowToolbarLabelStyle_fixed.zh-Hans.md) 和 [windowToolbarLabelStyle(_:)](scene/windowToolbarLabelStyle.zh-Hans.md) 等修饰符结合使用，可自定义由 SwiftUI 管理的窗口工具栏的外观。

## 类型属性

- **automatic**：自动标签样式。工具栏将使用最适合其所应用的 `Scene` 的 labelStyle。

- **iconOnly**：仅图标标签样式。工具栏内容将仅显示控件。

- **titleAndIcon**：标题和图标标签样式。工具栏内容将同时显示控件和标题。

- **titleOnly**：仅标题标签样式。工具栏内容将仅显示标题。

## 设置工具栏样式

- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的工具栏背景的首选形状样式。

- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的工具栏的首选配色方案。

- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的工具栏的首选前景样式。

- **windowToolbarStyle(_:)**：设置此场景中定义的工具栏的样式。

- **WindowToolbarStyle**：窗口工具栏外观和行为的规范。

- **toolbarLabelStyle**：应用于工具栏内控件的标签样式。

- **SpacerSizing**：定义间隔符如何自动调整大小的类型。

## 符合以下规范

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarLabelStyle
crawled: 2025-12-02T17:31:26Z
---

# ToolbarLabelStyle

**Structure**

The label style of a toolbar.

## Declaration

```swift
struct ToolbarLabelStyle
```

## Overview

Use this type in conjunction with modifiers like [windowToolbarLabelStyle(fixed:)](scene/windowToolbarLabelStyle_fixed.zh-Hans.md) and [windowToolbarLabelStyle(_:)](scene/windowToolbarLabelStyle.zh-Hans.md) to customize the appearance of window toolbars managed by SwiftUI.

## Type Properties

- **automatic**: The automatic label style. The toolbar will use a labelStyle that best fits the `Scene` it is applied to.
- **iconOnly**: The icon only label style. The toolbar contents will only display the control
- **titleAndIcon**: The title and icon label style. The toolbar contents will display both a control and title
- **titleOnly**: The title only label style. The toolbar contents will only display the title

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **SpacerSizing**: A type which defines how spacers should size themselves.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

