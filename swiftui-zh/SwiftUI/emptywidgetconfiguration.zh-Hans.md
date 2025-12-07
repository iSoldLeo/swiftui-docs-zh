--- 来源：https://developer.apple.com/documentation/swiftui/emptywidgetconfiguration
抓取时间：2025-12-04T13:10:19Z

---

# EmptyWidgetConfiguration

**Structure**

一个空的 Widget 配置。

## 声明

```swift
@frozen struct EmptyWidgetConfiguration
```

## 创建配置

- **init()**

## 创建 Widget

- **使用 WidgetKit 和 SwiftUI 构建 Widget**：创建 Widget，以便在主屏幕上显示应用内容，并可通过自定义 Intent 实现用户自定义设置。

- **创建 Widget 扩展**：在各种设备上以便捷、信息丰富的 Widget 形式显示应用内容。

- **保持组件更新**：规划组件的时间线，使用动态视图显示及时、相关的信息，并在信息发生变化时更新时间线。

- **创建可配置组件**：允许用户通过向项目中添加自定义应用意图来自定义组件。

- **Widget**：要在主屏幕或通知中心显示的组件的配置和内容。

- **WidgetBundle**：用于从单个组件扩展公开多个组件的容器。

- **LimitedAvailabilityConfiguration**：类型擦除后的组件配置。

- **WidgetConfiguration**：描述组件内容的类型。

## 符合以下规范

- BitwiseCopyable

- Copyable

- Sendable

- SendableMetatype

- WidgetConfiguration


---
source: https://developer.apple.com/documentation/swiftui/emptywidgetconfiguration
crawled: 2025-12-04T13:10:19Z
---

# EmptyWidgetConfiguration

**Structure**

An empty widget configuration.

## Declaration

```swift
@frozen struct EmptyWidgetConfiguration
```

## Creating a configuration

- **init()**

## Creating widgets

- **Building Widgets Using WidgetKit and SwiftUI**: Create widgets to show your app’s content on the Home screen, with custom intents for user-customizable settings.
- **Creating a widget extension**: Display your app’s content in a convenient, informative widget on various devices.
- **Keeping a widget up to date**: Plan your widget’s timeline to show timely, relevant information using dynamic views, and update the timeline when things change.
- **Making a configurable widget**: Give people the option to customize their widgets by adding a custom app intent to your project.
- **Widget**: The configuration and content of a widget to display on the Home screen or in Notification Center.
- **WidgetBundle**: A container used to expose multiple widgets from a single widget extension.
- **LimitedAvailabilityConfiguration**: A type-erased widget configuration.
- **WidgetConfiguration**: A type that describes a widget’s content.

## Conforms To

- BitwiseCopyable
- Copyable
- Sendable
- SendableMetatype
- WidgetConfiguration

