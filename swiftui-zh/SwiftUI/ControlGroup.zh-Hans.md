---
来源： https://developer.apple.com/documentation/SwiftUI/ControlGroup
抓取时间： 2025-12-02T17:26:44Z
---

# 控制组

**Structure**

容器视图，以适合上下文的视觉方式显示语义相关的控件

## 声明

```swift
struct ControlGroup<Content> where Content : View
```

## 概览

您可以为该视图提供一个描述其子视图的可选标签。该视图可根据周围环境以不同方式使用。例如，当您在工具栏项目中放置控件组时，SwiftUI 会在将控件组移动到工具栏的溢出菜单时使用该标签。

```swift
ContentView()
    .toolbar(id: "items") {
        ToolbarItem(id: "media") {
            ControlGroup {
                MediaButton()
                ChartButton()
                GraphButton()
            } label: {
                Label("Plus", systemImage: "plus")
            }
        }
    }
```

## 创建控制组

- **init(content:)**：创建带有指定子代的新控制组
- **init(content:label:)**：创建具有指定内容和标签的新控制组。
- **init(_:content:)**：创建具有指定内容的新控制组，该控制组的标签由字符串生成。

## 创建带有图像的控制组

- **init(_:image:content:)**：用指定的内容创建一个新的控制组，该控制组的标签由字符串和图像名称生成。
- **init(_:systemImage:content:)**：创建具有指定内容的新控制组，该控制组通过字符串和图像名称生成标签。

## 创建已配置的控制组

- **init(_:)**：根据样式配置创建控制组。

## 支持类型

- **LabeledControlGroupContent**：表示带有指定标签的控制组主体的视图。

## 呈现一组控件

- **controlGroupStyle(_:)**：设置该视图中控件组的样式。

## 符合

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroup
crawled: 2025-12-02T17:26:44Z
---

# ControlGroup

**Structure**

A container view that displays semantically-related controls in a visually-appropriate manner for the context

## Declaration

```swift
struct ControlGroup<Content> where Content : View
```

## Overview

You can provide an optional label to this view that describes its children. This view may be used in different ways depending on the surrounding context. For example, when you place the control group in a toolbar item, SwiftUI uses the label when the group is moved to the toolbar’s overflow menu.

```swift
ContentView()
    .toolbar(id: "items") {
        ToolbarItem(id: "media") {
            ControlGroup {
                MediaButton()
                ChartButton()
                GraphButton()
            } label: {
                Label("Plus", systemImage: "plus")
            }
        }
    }
```

## Creating a control group

- **init(content:)**: Creates a new ControlGroup with the specified children
- **init(content:label:)**: Creates a new control group with the specified content and a label.
- **init(_:content:)**: Creates a new control group with the specified content that generates its label from a string.

## Creating a control group with an image

- **init(_:image:content:)**: Creates a new control group with the specified content that generates its label from a string and image name.
- **init(_:systemImage:content:)**: Creates a new control group with the specified content that generates its label from a string and image name.

## Creating a configured control group

- **init(_:)**: Creates a control group based on a style configuration.

## Supporting types

- **LabeledControlGroupContent**: A view that represents the body of a control group with a specified label.

## Presenting a group of controls

- **controlGroupStyle(_:)**: Sets the style for control groups within this view.

## Conforms To

- View

