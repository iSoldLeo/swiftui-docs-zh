--- 来源：https://developer.apple.com/documentation/SwiftUI/View-configuration
抓取时间：2025-12-02T16:02:47Z

---

# 视图配置

**API 集合**

调整层级结构中视图的特性。

## 概述

SwiftUI 允许您使用视图修饰符来调整视图的外观和行为。

许多修饰符适用于特定类型的视图或行为，但也有一些修饰符更通用。例如，您可以通过动态设置视图的不透明度来有条件地隐藏任何视图，在用户将鼠标悬停在视图上时显示上下文帮助，或者请求视图的浅色或深色外观。

## 隐藏视图

- **opacity(_:)**：设置此视图的透明度。

- **hidden()**：无条件地隐藏此视图。

## 隐藏系统元素

- **labelsHidden()**：隐藏此视图中包含的所有控件的标签。

- **labelsVisibility(_:)**：控制此视图中包含的所有控件的标签的可见性。

- **labelsVisibility**：[labelsVisibility(_:)](View/labelsVisibility.zh-Hans.md) 设置的标签可见性。

- **menuIndicator(_:)**：设置此视图中控件的菜单指示器可见性。

- **statusBarHidden(_:)**：设置状态栏的可见性。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **Visibility**：UI 元素的可见性，根据平台、当前上下文和其他因素自动选择。

## 管理视图交互

- **disabled(_:)**：添加一个条件，用于控制用户是否可以与此视图进行交互。

- **isEnabled**：一个布尔值，指示与此环境关联的视图是否允许用户交互。

- **interactionActivityTrackingTag(_:)**：设置用于跟踪交互性的标签。

- **invalidatableContent(_:)**：标记接收者，因为他们的内容可能无效。

## 提供上下文帮助

- **help(_:)**：使用您提供的文本视图向视图添加帮助文本。

## 检测并请求浅色或深色外观

- **preferredColorScheme(_:)**：设置此演示的首选配色方案。

- **colorScheme**：此环境的配色方案。

- **ColorScheme**：对应于浅色和深色外观的可用配色方案。

## 获取配色方案对比度

- **colorSchemeContrast**：与此环境配色方案关联的对比度。

- **ColorSchemeContrast**：应用程序前景颜色和背景颜色之间的对比度。

## 配置视频直通

- **preferredSurroundingsEffect(_:)**：对视频直通应用效果。

- **SurroundingsEffect**：系统可以对视频直通应用的效果。

- **BreakthroughEffect**

## 编辑私密内容

- **为“始终显示”状态设计您的应用程序**：自定义 watchOS 应用程序的用户界面，使其能够持续显示。

- **privacySensitive(_:)**：将视图标记为包含敏感的私密用户数据。

- **redacted(reason:)**：为该视图层级添加一个需要进行信息编辑的原因。

- **unredacted()**：移除所有需要进行信息编辑的原因。

- **redactionReasons**：当前应用于该视图层级的信息编辑原因。

- **isSceneCaptured**：当前捕获状态。

- **RedactionReasons**：需要对屏幕上显示的数据进行信息编辑的原因。

## 视图

- **视图基础**：使用视图层级定义应用程序的视觉元素。

- **视图样式**：为不同类型的视图应用内置和自定义的外观和行为。

- **Animations**：根据状态变化创建平滑的视觉更新。

- **文本输入和输出**：显示格式化文本并获取用户输入的文本。

- **Images**：向应用程序的用户界面添加图像和符号。

- **控件和指示器**：显示数值并获取用户选择。

- **菜单和命令**：提供节省空间且上下文相关的命令和控件访问方式。

- **Shapes**：使用颜色、渐变或其他图案描绘和填充内置和自定义形状。

- **绘图和图形**：使用图形效果和自定义绘图增强视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View-configuration
crawled: 2025-12-02T16:02:47Z
---

# View configuration

**API Collection**

Adjust the characteristics of views in a hierarchy.

## Overview

SwiftUI enables you to tune the appearance and behavior of views using view modifiers.



Many modifiers apply to specific kinds of views or behaviors, but some apply more generally. For example, you can conditionally hide any view by dynamically setting its opacity, display contextual help when people hover over a view, or request the light or dark appearance for a view.

## Hiding views

- **opacity(_:)**: Sets the transparency of this view.
- **hidden()**: Hides this view unconditionally.

## Hiding system elements

- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **labelsVisibility(_:)**: Controls the visibility of labels of any controls contained within this view.
- **labelsVisibility**: The labels visibility set by [labelsVisibility(_:)](View/labelsVisibility.zh-Hans.md).
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **statusBarHidden(_:)**: Sets the visibility of the status bar.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **Visibility**: The visibility of a UI element, chosen automatically based on the platform, current context, and other factors.

## Managing view interaction

- **disabled(_:)**: Adds a condition that controls whether users can interact with this view.
- **isEnabled**: A Boolean value that indicates whether the view associated with this environment allows user interaction.
- **interactionActivityTrackingTag(_:)**: Sets a tag that you use for tracking interactivity.
- **invalidatableContent(_:)**: Mark the receiver as their content might be invalidated.

## Providing contextual help

- **help(_:)**: Adds help text to a view using a text view that you provide.

## Detecting and requesting the light or dark appearance

- **preferredColorScheme(_:)**: Sets the preferred color scheme for this presentation.
- **colorScheme**: The color scheme of this environment.
- **ColorScheme**: The possible color schemes, corresponding to the light and dark appearances.

## Getting the color scheme contrast

- **colorSchemeContrast**: The contrast associated with the color scheme of this environment.
- **ColorSchemeContrast**: The contrast between the app’s foreground and background colors.

## Configuring passthrough

- **preferredSurroundingsEffect(_:)**: Applies an effect to passthrough video.
- **SurroundingsEffect**: Effects that the system can apply to passthrough video.
- **BreakthroughEffect**

## Redacting private content

- **Designing your app for the Always On state**: Customize your watchOS app’s user interface for continuous display.
- **privacySensitive(_:)**: Marks the view as containing sensitive, private user data.
- **redacted(reason:)**: Adds a reason to apply a redaction to this view hierarchy.
- **unredacted()**: Removes any reason to apply a redaction to this view hierarchy.
- **redactionReasons**: The current redaction reasons applied to the view hierarchy.
- **isSceneCaptured**: The current capture state.
- **RedactionReasons**: The reasons to apply a redaction to data displayed on screen.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View styles**: Apply built-in and custom appearances and behaviors to different types of views.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

