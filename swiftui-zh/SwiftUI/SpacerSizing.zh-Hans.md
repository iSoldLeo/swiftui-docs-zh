---
来源： https://developer.apple.com/documentation/SwiftUI/SpacerSizing
抓取时间： 2025-12-02T17:31:27Z
---

# 间隔尺寸

**Structure**

定义间隔条尺寸大小的类型。

## 声明

```swift
struct SpacerSizing
```

## 概览

该类型与 [ToolbarSpacer](ToolbarSpacer.zh-Hans.md) 类型配合使用，可定义间隔条是灵活尺寸，还是使用系统定义的尺寸规则的固定尺寸。

例如，下面的代码在工具栏中的 "共享 "和 "更多 "按钮之间添加了一个固定大小的工具栏间隔条：

```swift
ContentView()
    .toolbar(id: "main-toolbar") {
        ToolbarItem(id: "tag") {
           TagButton()
        }
        ToolbarItem(id: "share") {
           ShareButton()
        }
        ToolbarSpacer(.fixed)
        ToolbarItem(id: "more") {
           MoreButton()
        }
    }
```

## 类型属性

- **fixed**：固定间隔条尺寸行为。间隔条将使用由系统和间隔条使用环境决定的预定义尺寸。
- **flexible**：灵活的间隔条尺寸行为。空间隔离器将根据当前上下文所提供的空间大小进行扩展。

## 工具栏样式

- **toolbarBackground(_:for:)**：指定由 SwiftUI 管理的工具栏背景的首选形状样式。
- **toolbarColorScheme(_:for:)**：指定由 SwiftUI 管理的条形图的首选配色方案。
- **toolbarForegroundStyle(_:for:)**：指定由 SwiftUI 管理的条形图的首选前景样式。
- **windowToolbarStyle(_:)**：为在此场景中定义的工具栏设置样式。
- **WindowToolbarStyle**：窗口工具栏的外观和行为规范。
- **toolbarLabelStyle**：应用于工具栏中控件的标签样式。
- **ToolbarLabelStyle**：工具栏的标签样式。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/SpacerSizing
crawled: 2025-12-02T17:31:27Z
---

# SpacerSizing

**Structure**

A type which defines how spacers should size themselves.

## Declaration

```swift
struct SpacerSizing
```

## Overview

Use this type in coordination with the [ToolbarSpacer](ToolbarSpacer.zh-Hans.md) type to define if the spacer should be a flexible size, or a fixed size using system-defined sizing rules.

For example, the following adds a fixed-size toolbar spacer between the share and more buttons in the toolbar:

```swift
ContentView()
    .toolbar(id: "main-toolbar") {
        ToolbarItem(id: "tag") {
           TagButton()
        }
        ToolbarItem(id: "share") {
           ShareButton()
        }
        ToolbarSpacer(.fixed)
        ToolbarItem(id: "more") {
           MoreButton()
        }
    }
```

## Type Properties

- **fixed**: The fixed spacer sizing behavior. The spacer will use a pre-defined size determined by the system and the context in which the spacer is used.
- **flexible**: The flexible spacer sizing behavior. The spacer will expand to accommodate as much space as it is given in the current context.

## Styling a toolbar

- **toolbarBackground(_:for:)**: Specifies the preferred shape style of the background of a bar managed by SwiftUI.
- **toolbarColorScheme(_:for:)**: Specifies the preferred color scheme of a bar managed by SwiftUI.
- **toolbarForegroundStyle(_:for:)**: Specifies the preferred foreground style of bars managed by SwiftUI.
- **windowToolbarStyle(_:)**: Sets the style for the toolbar defined within this scene.
- **WindowToolbarStyle**: A specification for the appearance and behavior of a window’s toolbar.
- **toolbarLabelStyle**: The label style to apply to controls within a toolbar.
- **ToolbarLabelStyle**: The label style of a toolbar.

## Conforms To

- Sendable
- SendableMetatype

