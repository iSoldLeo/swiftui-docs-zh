---

来源：https://developer.apple.com/documentation/SwiftUI/View-styles
抓取时间：2025-12-02T16:02:47Z

---

# 视图样式

**API 集合**

将内置和自定义的外观和行为应用于不同类型的视图。

## 概述

SwiftUI 为某些类型的视图定义了内置样式，并根据特定的显示上下文自动选择合适的样式。例如，[Label](Label.zh-Hans.md) 可能显示为图标、字符串标题或两者兼有，具体取决于平台、视图是否显示在工具栏中等因素。

您可以使用样式视图修饰符来覆盖自动样式。这些修饰符通常会在整个容器视图中传播，因此您可以将视图层次结构包装在样式修饰符中，以影响层次结构中给定类型的所有视图。

任何定义了 `makeBody(configuration:)` 方法的样式协议（例如 [ToggleStyle](ToggleStyle.zh-Hans.md)）都允许您定义自定义样式。创建一个符合相应样式协议的类型，并实现其 `makeBody(configuration:)` 方法。然后，使用样式视图修饰符应用新样式，就像应用内置样式一样。

## 使用 Liquid Glass 设置视图样式

- **将 Liquid Glass 应用于自定义视图**：使用 Liquid Glass 效果配置、组合和变形视图。

- **里程碑：使用 Liquid Glass 构建应用**：使用系统提供的和自定义的 Liquid Glass 增强您的应用体验。

- **glassEffect(_:in:)**：将 Liquid Glass 效果应用于视图。

- **interactive(_:)**：返回配置为交互式的结构副本。

- **GlassEffectContainer**：将多个液态玻璃形状组合成一个单一形状的视图，该单一形状可以相互变形。

- **GlassEffectTransition**：描述在视图层级结构中添加或移除玻璃效果时要应用的更改的结构。

- **GlassButtonStyle**：根据按钮上下文应用玻璃边框图案的按钮样式。

- **GlassProminentButtonStyle**：根据按钮上下文应用醒目玻璃边框图案的按钮样式。

- **DefaultGlassEffectShape**：玻璃效果应用的默认形状，即胶囊体。

## 按钮样式

- **buttonStyle(_:)**：将此视图中按钮的样式设置为具有自定义外观和标准交互行为的按钮样式。

- **ButtonStyle**：一种类型，用于为视图层次结构中的所有按钮应用标准交互行为和自定义外观。

- **ButtonStyleConfiguration**：按钮的属性。

- **PrimitiveButtonStyle**：一种类型，用于为视图层次结构中的所有按钮应用自定义交互行为和自定义外观。

- **PrimitiveButtonStyleConfiguration**：按钮的属性。

- **signInWithAppleButtonStyle(_:)**：设置用于显示控件的样式（参见 `SignInWithAppleButton.Style`）。

## 选择器样式

- **pickerStyle(_:)**：设置此视图中选择器的样式。

- **PickerStyle**：一种类型，用于指定视图层次结构中所有选择器的外观和交互方式。

- **datePickerStyle(_:)**：设置此视图中日期选择器的样式。

- **DatePickerStyle**：指定视图层级结构中所有日期选择器的外观和交互方式的类型。

## 菜单样式

- **menuStyle(_:)**：设置此视图中菜单的样式。

- **MenuStyle**：将标准交互行为和自定义外观应用于视图层级结构中所有菜单的类型。

- **MenuStyleConfiguration**：菜单的配置。

## 切换按钮样式

- **toggleStyle(_:)**：设置视图层级结构中切换按钮的样式。

- **ToggleStyle**：切换按钮的外观和行为。

- **ToggleStyleConfiguration**：切换实例的属性。

## 指示器样式

- **gaugeStyle(_:)**：设置此视图中仪表盘的样式。

- **GaugeStyle**：定义视图层次结构中所有仪表盘实例的实现。

- **GaugeStyleConfiguration**：仪表盘实例的属性。

- **progressViewStyle(_:)**：设置此视图中进度视图的样式。

- **ProgressViewStyle**：一种将标准交互行为应用于视图层次结构中所有进度视图的类型。

- **ProgressViewStyleConfiguration**：进度视图实例的属性。

## 显示文本的视图样式

- **labelStyle(_:)**：设置此视图中标签的样式。

- **LabelStyle**：一种为视图内所有标签应用自定义外观的类型。

- **LabelStyleConfiguration**：标签的属性。

- **textFieldStyle(_:)**：设置此视图中文本字段的样式。

- **TextFieldStyle**：文本字段外观和交互的规范。

- **textEditorStyle(_:)**：设置此视图中文本编辑器的样式。

- **TextEditorStyle**：文本编辑器外观和交互的规范。

- **TextEditorStyleConfiguration**：文本编辑器的属性。

## 设置集合视图的样式

- **listStyle(_:)**：设置此视图中列表的样式。

- **ListStyle**：描述列表行为和外观的协议。

- **tableStyle(_:)**：设置此视图中表格的样式。

- **TableStyle**：将自定义外观应用于视图中所有表格的类型。

- **TableStyleConfiguration**：表格的属性。

- **disclosureGroupStyle(_:)**：设置此视图中展开组的样式。

- **DisclosureGroupStyle**：指定视图层次结构中展开组的外观和交互的类型。

## 设置导航视图样式

- **navigationSplitViewStyle(_:)**：设置此视图中导航拆分视图的样式。

- **NavigationSplitViewStyle**：指定视图层次结构中导航拆分视图的外观和交互的类型。

- **tabViewStyle(_:)**：设置当前环境中选项卡视图的样式。

- **TabViewStyle**：选项卡视图的外观和交互规范。

## 样式组

- **controlGroupStyle(_:)**：设置此视图中控件组的样式。

- **ControlGroupStyle**：定义视图层次结构中所有控件组的实现。

- **ControlGroupStyleConfiguration**：控件组的属性。

- **formStyle(_:)**：设置视图层次结构中窗体的样式。

- **FormStyle**：窗体的外观和行为。

- **FormStyleConfiguration**：窗体实例的属性。

- **groupBoxStyle(_:)**：设置此视图中分组框的样式。

- **GroupBoxStyle**：指定视图层次结构中所有分组框的外观和交互方式的类型。

- **GroupBoxStyleConfiguration**：分组框实例的属性。

- **indexViewStyle(_:)**：设置当前环境中索引视图的样式。

- **IndexViewStyle**：定义视图层次结构中所有 `IndexView` 实例的实现。

- **labeledContentStyle(_:)**：设置带标签内容的样式。

- **LabeledContentStyle**：带标签内容实例的外观和行为。

- **LabeledContentStyleConfiguration**：带标签内容实例的属性。

## 从窗口内的视图设置窗口样式

- **presentedWindowStyle(_:)**：设置通过与此视图交互创建的窗口的样式。

- **presentedWindowToolbarStyle(_:)**：设置通过与此视图交互创建的窗口中工具栏的样式。

## 在 visionOS 中为视图添加玻璃背景

- **glassBackgroundEffect(displayMode:)**：使用自动玻璃背景效果和相对于容器的圆角矩形形状填充视图的背景。

- **glassBackgroundEffect(in:displayMode:)**：使用自动玻璃背景效果和您指定的形状填充视图的背景。

- **GlassBackgroundDisplayMode**：玻璃背景的显示模式。

- **GlassBackgroundEffect**：玻璃背景外观的规范。

- **AutomaticGlassBackgroundEffect**：自动玻璃背景效果。

- **GlassBackgroundEffectConfiguration**：用于构建自定义效果的配置。

- **FeatheredGlassBackgroundEffect**：羽化玻璃背景效果。

- **PlateGlassBackgroundEffect**：平板玻璃背景效果。

## 视图

- **视图基础**：使用视图层级结构定义应用程序的视觉元素。

- **视图配置**：调整层级结构中视图的特性。

- **Animations**：响应状态变化，实现平滑的视觉更新。

- **文本输入输出**：显示格式化文本并获取用户输入的文本。

- **Images**：向应用程序的用户界面添加图像和符号。

- **控件和指示器**：显示值并获取用户选择。

- **菜单和命令**：提供节省空间且上下文相关的命令和控件访问方式。

- **Shapes**：使用颜色、渐变或其他图案描绘并填充内置和自定义形状。

- **绘图和图形**：使用图形效果和自定义绘图增强您的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/View-styles
crawled: 2025-12-02T16:02:47Z
---

# View styles

**API Collection**

Apply built-in and custom appearances and behaviors to different types of views.

## Overview

SwiftUI defines built-in styles for certain kinds of views and automatically selects the appropriate style for a particular presentation context. For example, a [Label](Label.zh-Hans.md) might appear as an icon, a string title, or both, depending on factors like the platform, whether the view appears in a toolbar, and so on.



You can override the automatic style by using one of the style view modifiers. These modifiers typically propagate throughout a container view, so that you can wrap a view hierarchy in a style modifier to affect all the views of the given type within the hierarchy.

Any of the style protocols that define a `makeBody(configuration:)` method, like [ToggleStyle](ToggleStyle.zh-Hans.md), also enable you to define custom styles. Create a type that conforms to the corresponding style protocol and implement its `makeBody(configuration:)` method. Then apply the new style using a style view modifier exactly like a built-in style.

## Styling views with Liquid Glass

- **Applying Liquid Glass to custom views**: Configure, combine, and morph views using Liquid Glass effects.
- **Landmarks: Building an app with Liquid Glass**: Enhance your app experience with system-provided and custom Liquid Glass.
- **glassEffect(_:in:)**: Applies the Liquid Glass effect to a view.
- **interactive(_:)**: Returns a copy of the structure configured to be interactive.
- **GlassEffectContainer**: A view that combines multiple Liquid Glass shapes into a single shape that can morph individual shapes into one another.
- **GlassEffectTransition**: A structure that describes changes to apply when a glass effect is added or removed from the view hierarchy.
- **GlassButtonStyle**: A button style that applies glass border artwork based on the button’s context.
- **GlassProminentButtonStyle**: A button style that applies prominent glass border artwork based on the button’s context.
- **DefaultGlassEffectShape**: The default shape applied by glass effects, a capsule.

## Styling buttons

- **buttonStyle(_:)**: Sets the style for buttons within this view to a button style with a custom appearance and standard interaction behavior.
- **ButtonStyle**: A type that applies standard interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **ButtonStyleConfiguration**: The properties of a button.
- **PrimitiveButtonStyle**: A type that applies custom interaction behavior and a custom appearance to all buttons within a view hierarchy.
- **PrimitiveButtonStyleConfiguration**: The properties of a button.
- **signInWithAppleButtonStyle(_:)**: Sets the style used for displaying the control (see `SignInWithAppleButton.Style`).

## Styling pickers

- **pickerStyle(_:)**: Sets the style for pickers within this view.
- **PickerStyle**: A type that specifies the appearance and interaction of all pickers within a view hierarchy.
- **datePickerStyle(_:)**: Sets the style for date pickers within this view.
- **DatePickerStyle**: A type that specifies the appearance and interaction of all date pickers within a view hierarchy.

## Styling menus

- **menuStyle(_:)**: Sets the style for menus within this view.
- **MenuStyle**: A type that applies standard interaction behavior and a custom appearance to all menus within a view hierarchy.
- **MenuStyleConfiguration**: A configuration of a menu.

## Styling toggles

- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.
- **ToggleStyle**: The appearance and behavior of a toggle.
- **ToggleStyleConfiguration**: The properties of a toggle instance.

## Styling indicators

- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **GaugeStyle**: Defines the implementation of all gauge instances within a view hierarchy.
- **GaugeStyleConfiguration**: The properties of a gauge instance.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **ProgressViewStyle**: A type that applies standard interaction behavior to all progress views within a view hierarchy.
- **ProgressViewStyleConfiguration**: The properties of a progress view instance.

## Styling views that display text

- **labelStyle(_:)**: Sets the style for labels within this view.
- **LabelStyle**: A type that applies a custom appearance to all labels within a view.
- **LabelStyleConfiguration**: The properties of a label.
- **textFieldStyle(_:)**: Sets the style for text fields within this view.
- **TextFieldStyle**: A specification for the appearance and interaction of a text field.
- **textEditorStyle(_:)**: Sets the style for text editors within this view.
- **TextEditorStyle**: A specification for the appearance and interaction of a text editor.
- **TextEditorStyleConfiguration**: The properties of a text editor.

## Styling collection views

- **listStyle(_:)**: Sets the style for lists within this view.
- **ListStyle**: A protocol that describes the behavior and appearance of a list.
- **tableStyle(_:)**: Sets the style for tables within this view.
- **TableStyle**: A type that applies a custom appearance to all tables within a view.
- **TableStyleConfiguration**: The properties of a table.
- **disclosureGroupStyle(_:)**: Sets the style for disclosure groups within this view.
- **DisclosureGroupStyle**: A type that specifies the appearance and interaction of disclosure groups within a view hierarchy.

## Styling navigation views

- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **NavigationSplitViewStyle**: A type that specifies the appearance and interaction of navigation split views within a view hierarchy.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.
- **TabViewStyle**: A specification for the appearance and interaction of a tab view.

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
- **IndexViewStyle**: Defines the implementation of all `IndexView` instances within a view hierarchy.
- **labeledContentStyle(_:)**: Sets a style for labeled content.
- **LabeledContentStyle**: The appearance and behavior of a labeled content instance..
- **LabeledContentStyleConfiguration**: The properties of a labeled content instance.

## Styling windows from a view inside the window

- **presentedWindowStyle(_:)**: Sets the style for windows created by interacting with this view.
- **presentedWindowToolbarStyle(_:)**: Sets the style for the toolbar in windows created by interacting with this view.

## Adding a glass background on views in visionOS

- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.
- **GlassBackgroundDisplayMode**: The display mode of a glass background.
- **GlassBackgroundEffect**: A specification for the appearance of a glass background.
- **AutomaticGlassBackgroundEffect**: The automatic glass background effect.
- **GlassBackgroundEffectConfiguration**: A configuration used to build a custom effect.
- **FeatheredGlassBackgroundEffect**: The feathered glass background effect.
- **PlateGlassBackgroundEffect**: The plate glass background effect.

## Views

- **View fundamentals**: Define the visual elements of your app using a hierarchy of views.
- **View configuration**: Adjust the characteristics of views in a hierarchy.
- **Animations**: Create smooth visual updates in response to state changes.
- **Text input and output**: Display formatted text and get text input from the user.
- **Images**: Add images and symbols to your app’s user interface.
- **Controls and indicators**: Display values and get user selections.
- **Menus and commands**: Provide space-efficient, context-dependent access to commands and controls.
- **Shapes**: Trace and fill built-in and custom shapes with a color, gradient, or other pattern.
- **Drawing and graphics**: Enhance your views with graphical effects and customized drawings.

