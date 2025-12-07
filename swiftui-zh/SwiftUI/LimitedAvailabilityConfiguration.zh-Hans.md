--- 来源：https://developer.apple.com/documentation/SwiftUI/LimitedAvailabilityConfiguration
抓取时间：2025-12-02T17:31:58Z

---

# LimitedAvailabilityConfiguration

**Structure**

类型已擦除的组件配置。

## 声明

```swift
@MainActor @frozen @preconcurrency struct LimitedAvailabilityConfiguration
```

## 概述

您不能直接使用此类型。SwiftUI 会代表您创建此类型。

## 创建组件

- **使用 WidgetKit 和 SwiftUI 构建组件**：创建组件以在主屏幕上显示应用内容，并可通过自定义 Intent 实现用户自定义设置。

- **创建组件扩展**：在各种设备上以便捷、信息丰富的组件形式显示应用内容。

- **保持小部件更新**：规划小部件的时间线，使用动态视图显示及时、相关的信息，并在信息发生变化时更新时间线。

- **创建可配置的小部件**：允许用户通过向项目中添加自定义应用意图来自定义小部件。

- **Widget**：要在主屏幕或通知中心显示的小部件的配置和内容。

- **WidgetBundle**：用于从单个小部件扩展公开多个小部件的容器。

- **WidgetConfiguration**：描述小部件内容的类型。

- **EmptyWidgetConfiguration**：空的小部件配置。

## 符合以下规范

- WidgetConfiguration


---
source: https://developer.apple.com/documentation/SwiftUI/LimitedAvailabilityConfiguration
crawled: 2025-12-02T17:31:58Z
---

# LimitedAvailabilityConfiguration

**Structure**

A type-erased widget configuration.

## Declaration

```swift
@MainActor @frozen @preconcurrency struct LimitedAvailabilityConfiguration
```

## Overview

You don’t use this type directly. Instead SwiftUI creates this type on your behalf.

## Creating widgets

- **Building Widgets Using WidgetKit and SwiftUI**: Create widgets to show your app’s content on the Home screen, with custom intents for user-customizable settings.
- **Creating a widget extension**: Display your app’s content in a convenient, informative widget on various devices.
- **Keeping a widget up to date**: Plan your widget’s timeline to show timely, relevant information using dynamic views, and update the timeline when things change.
- **Making a configurable widget**: Give people the option to customize their widgets by adding a custom app intent to your project.
- **Widget**: The configuration and content of a widget to display on the Home screen or in Notification Center.
- **WidgetBundle**: A container used to expose multiple widgets from a single widget extension.
- **WidgetConfiguration**: A type that describes a widget’s content.
- **EmptyWidgetConfiguration**: An empty widget configuration.

## Conforms To

- WidgetConfiguration

