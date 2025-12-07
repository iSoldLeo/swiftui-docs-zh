--- 来源：https://developer.apple.com/documentation/SwiftUI/View-Appearance
抓取时间：2025-12-02T17:22:09Z

---

# 外观修饰符

**API 集合**

配置视图的前景色和背景样式、控件以及可见性。

## 概述

使用这些修饰符配置视图的外观，包括颜色和色调的使用，以及叠加层和背景元素的应用。控制视图及其内部特定元素的可见性。管理各种控件的形状和大小。

有关配置视图的信息，请参阅 [View-configuration](View-configuration.zh-Hans.md)。

## 颜色和图案

- **backgroundStyle(_:)**：设置指定的样式以渲染视图中的背景。

- **foregroundStyle(_:)**：设置视图的前景色元素使用指定的样式。

- **foregroundStyle(_:_:)**：设置子视图中前景色样式的主样式和次样式级别。

- **foregroundStyle(_:_:_:)**：设置前景色样式的主样式、次样式和三级样式。

- **allowedDynamicRange(_:)**：返回一个配置了指定动态范围的新视图。

## 色调

- **tint(_:)**：设置此视图中的色调颜色。

- **listRowSeparatorTint(_:edges:)**：设置与行关联的色调颜色。

- **listSectionSeparatorTint(_:edges:)**：设置与部分关联的色调颜色。

- **listItemTint(_:)**：为列表中的内容设置固定色调。

## 浅色和深色外观

- **preferredColorScheme(_:)**：设置此演示文稿的首选配色方案。

- **preferredSurroundingsEffect(_:)**：为穿透视频应用效果。

## 前景元素

- **border(_:width:)**：为此视图添加指定样式和宽度的边框。

- **overlay(alignment:content:)**：将您指定的视图叠加到此视图的前面。

- **overlay(_:ignoresSafeAreaEdges:)**：将指定的样式叠加到此视图的前面。

- **overlay(_:in:fillStyle:)**：将您指定的形状叠加到此视图的前面。

## 背景元素

- **background(alignment:content:)**：将您指定的视图置于此视图的下方。

- **background(_:ignoresSafeAreaEdges:)**：将视图的背景设置为指定样式。

- **background(ignoresSafeAreaEdges:)**：将视图的背景设置为默认背景样式。

- **background(_:in:fillStyle:)**：将视图的背景设置为填充指定样式的可插入形状。

- **background(in:fillStyle:)**：将视图的背景设置为填充默认背景样式的可插入形状。

- **alternatingRowBackgrounds(_:)**：覆盖此视图中的列表和表格是否具有交替的行背景。

- **listRowBackground(_:)**：在列表行项的后面放置自定义背景视图。

- **scrollContentBackground(_:)**：指定此视图内可滚动视图的背景可见性。

- **containerBackground(_:for:)**：设置包含视图的容器的背景。

- **containerBackground(for:alignment:content:)**：设置包含视图的容器的背景。

- **glassBackgroundEffect(displayMode:)**：使用自动玻璃背景效果和相对于容器的圆角矩形形状填充视图的背景。

- **glassBackgroundEffect(in:displayMode:)**：使用自动玻璃背景效果和您指定的形状填充视图的背景。

## 控件配置

- **defaultWheelPickerItemHeight(_:)**：设置默认的滚轮式选择器项目高度。

- **horizontalRadioGroupLayout()**：设置此视图中单选按钮组的样式，使其与布局内的单选按钮水平对齐。

- **controlSize(_:)**：设置此视图中控件的大小。

- **buttonBorderShape(_:)**：设置此视图中按钮的边框形状。

- **buttonRepeatBehavior(_:)**：设置此视图中的按钮在长时间交互后是否应重复触发其操作。

- **headerProminence(_:)**：设置此视图的标题突出显示程度。

- **scrollDisabled(_:)**：禁用或启用可滚动视图中的滚动。

- **scrollBounceBehavior(_:axes:)**：配置可滚动视图沿指定轴的回弹行为。

- **scrollIndicatorsFlash(onAppear:)**：当可滚动视图出现时，闪烁其滚动指示器。

- **scrollIndicatorsFlash(trigger:)**：当可滚动视图中的值发生变化时，闪烁其滚动指示器。

- **menuOrder(_:)**：设置从此视图显示的菜单项的首选顺序。

- **menuActionDismissBehavior(_:)**：告知菜单在执行操作后是否关闭。

- **paletteSelectionEffect(_:)**：指定要应用于调色板项的选择效果。

- **typeSelectEquivalent(_:)**：在集合（例如列表或表格）中设置显式类型选择等效文本。

## 符号效果

- **symbolEffect(_:options:isActive:)**：返回一个添加了符号效果的新视图。

- **symbolEffect(_:options:value:)**：返回一个添加了符号效果的新视图。

- **symbolEffectsRemoved(_:)**：返回一个继承了符号图像效果的新视图，该效果可能被移除或保持不变。

## 隐私和编辑

- **privacySensitive(_:)**：将此视图标记为包含敏感的私人用户数据。

- **redacted(reason:)**：添加对该视图层级应用编辑的原因。

- **unredacted()**：移除对该视图层级应用编辑的任何原因。

- **invalidatableContent(_:)**：将接收者标记为其内容可能无效。

## 可见性

- **hidden()**：无条件隐藏此视图。

- **labelsHidden()**：隐藏此视图中所有控件的标签。

- **menuIndicator(_:)**：设置此视图中控件的菜单指示器可见性。

- **listRowSeparator(_:edges:)**：设置与此特定行关联的分隔符的显示模式。

- **listSectionSeparator(_:edges:)**：设置是否隐藏与列表部分关联的分隔符。

- **persistentSystemOverlays(_:)**：设置覆盖在应用程序上的非瞬态系统视图的首选可见性。

- **scrollIndicators(_:axes:)**：设置此视图中滚动指示器的可见性。

- **scrollClipDisabled(_:)**：设置滚动视图是否将其内容裁剪到其边界。

- **tableColumnHeaders(_:)**：控制 `Table` 的列标题视图的可见性。

- **upperLimbVisibility(_:)**：设置呈现 [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) 场景时用户上肢的首选可见性。

- **volumeBaseplateVisibility(_:)**：设置体素底板的可见性，该底板会在用户看向体素的“底部”以及调整大小时显示。`automatic` 和 `visible` 都会显示底板。`hidden` 则永远不会显示底板。

## 感官反馈

- **sensoryFeedback(_:trigger:)**：当提供的 `trigger` 值发生变化时，播放指定的 `feedback`。

- **sensoryFeedback(trigger:_:)**：当提供的 `trigger` 值发生变化后，`feedback` 闭包返回时，播放反馈。

- **sensoryFeedback(_:trigger:condition:)**：当提供的 `trigger` 值发生变化且 `condition` 闭包返回 `true` 时，播放指定的 `feedback`。

## 小部件配置

- **widgetAccentable(_:)**：将视图及其所有子视图添加到带重音符号的组中。

- **widgetCurvesContent(_:)**：如果上下文允许，则沿曲线显示组件内容。

- **widgetLabel(_:)**：返回一个本地化的文本标签，用于在辅助组件主 SwiftUI 视图之外显示附加内容。

- **widgetLabel(label:)**：创建一个标签，用于在辅助组件主 SwiftUI 视图之外显示附加内容。

- **dynamicIsland(verticalPlacement:)**：指定动态岛中显示的已展开 Live Activity 视图的垂直位置。

- **accessoryWidgetGroupStyle(_:)**：可应用于 `AccessoryWidgetGroup` 的视图修饰符，用于指定三个内容视图的遮罩形状。 `style` 的值设置为 `.automatic`，其默认值为 `.circular`。

## 窗口行为

- **windowDismissBehavior(_:)**：配置包含 `self` 的窗口的关闭功能。

- **windowFullScreenBehavior(_:)**：配置包含 `self` 的窗口的全屏功能。

- **windowMinimizeBehavior(_:)**：配置包含 `self` 的窗口的最小化功能。

- **windowResizeBehavior(_:)**：配置包含 `self` 的窗口的调整大小功能。

## 配置视图元素

- **辅助功能修饰符**：让您的 SwiftUI 应用对所有人（包括残障人士）都易于访问。

- **文本和符号修饰符**：管理视图中文本的渲染、选择和输入。

- **辅助视图修饰符**：添加和配置辅助视图，例如工具栏和上下文菜单。

- **图表视图修饰符**：配置您使用 Swift Charts 声明的图表。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Appearance
crawled: 2025-12-02T17:22:09Z
---

# Appearance modifiers

**API Collection**

Configure a view’s foreground and background styles, controls, and visibility.

## Overview

Use these modifiers to configure the appearance of a view, including the use of color and tint, and the application of overlays and background elements. Control the visibility of a view and specific elements within a view. Manage the shape and size of various controls.

For information about configuring views, see [View-configuration](View-configuration.zh-Hans.md).

## Colors and patterns

- **backgroundStyle(_:)**: Sets the specified style to render backgrounds within the view.
- **foregroundStyle(_:)**: Sets a view’s foreground elements to use a given style.
- **foregroundStyle(_:_:)**: Sets the primary and secondary levels of the foreground style in the child view.
- **foregroundStyle(_:_:_:)**: Sets the primary, secondary, and tertiary levels of the foreground style.
- **allowedDynamicRange(_:)**: Returns a new view configured with the specified allowed dynamic range.

## Tint

- **tint(_:)**: Sets the tint color within this view.
- **listRowSeparatorTint(_:edges:)**: Sets the tint color associated with a row.
- **listSectionSeparatorTint(_:edges:)**: Sets the tint color associated with a section.
- **listItemTint(_:)**: Sets a fixed tint color for content in a list.

## Light and dark appearance

- **preferredColorScheme(_:)**: Sets the preferred color scheme for this presentation.
- **preferredSurroundingsEffect(_:)**: Applies an effect to passthrough video.

## Foreground elements

- **border(_:width:)**: Adds a border to this view with the specified style and width.
- **overlay(alignment:content:)**: Layers the views that you specify in front of this view.
- **overlay(_:ignoresSafeAreaEdges:)**: Layers the specified style in front of this view.
- **overlay(_:in:fillStyle:)**: Layers a shape that you specify in front of this view.

## Background elements

- **background(alignment:content:)**: Layers the views that you specify behind this view.
- **background(_:ignoresSafeAreaEdges:)**: Sets the view’s background to a style.
- **background(ignoresSafeAreaEdges:)**: Sets the view’s background to the default background style.
- **background(_:in:fillStyle:)**: Sets the view’s background to an insettable shape filled with a style.
- **background(in:fillStyle:)**: Sets the view’s background to an insettable shape filled with the default background style.
- **alternatingRowBackgrounds(_:)**: Overrides whether lists and tables in this view have alternating row backgrounds.
- **listRowBackground(_:)**: Places a custom background view behind a list row item.
- **scrollContentBackground(_:)**: Specifies the visibility of the background for scrollable views within this view.
- **containerBackground(_:for:)**: Sets the container background of the enclosing container using a view.
- **containerBackground(for:alignment:content:)**: Sets the container background of the enclosing container using a view.
- **glassBackgroundEffect(displayMode:)**: Fills the view’s background with an automatic glass background effect and container-relative rounded rectangle shape.
- **glassBackgroundEffect(in:displayMode:)**: Fills the view’s background with an automatic glass background effect and a shape that you specify.

## Control configuration

- **defaultWheelPickerItemHeight(_:)**: Sets the default wheel-style picker item height.
- **horizontalRadioGroupLayout()**: Sets the style for radio group style pickers within this view to be horizontally positioned with the radio buttons inside the layout.
- **controlSize(_:)**: Sets the size for controls within this view.
- **buttonBorderShape(_:)**: Sets the border shape for buttons in this view.
- **buttonRepeatBehavior(_:)**: Sets whether buttons in this view should repeatedly trigger their actions on prolonged interactions.
- **headerProminence(_:)**: Sets the header prominence for this view.
- **scrollDisabled(_:)**: Disables or enables scrolling in scrollable views.
- **scrollBounceBehavior(_:axes:)**: Configures the bounce behavior of scrollable views along the specified axis.
- **scrollIndicatorsFlash(onAppear:)**: Flashes the scroll indicators of a scrollable view when it appears.
- **scrollIndicatorsFlash(trigger:)**: Flashes the scroll indicators of scrollable views when a value changes.
- **menuOrder(_:)**: Sets the preferred order of items for menus presented from this view.
- **menuActionDismissBehavior(_:)**: Tells a menu whether to dismiss after performing an action.
- **paletteSelectionEffect(_:)**: Specifies the selection effect to apply to a palette item.
- **typeSelectEquivalent(_:)**: Sets an explicit type select equivalent text in a collection, such as a list or table.

## Symbol effects

- **symbolEffect(_:options:isActive:)**: Returns a new view with a symbol effect added to it.
- **symbolEffect(_:options:value:)**: Returns a new view with a symbol effect added to it.
- **symbolEffectsRemoved(_:)**: Returns a new view with its inherited symbol image effects either removed or left unchanged.

## Privacy and redaction

- **privacySensitive(_:)**: Marks the view as containing sensitive, private user data.
- **redacted(reason:)**: Adds a reason to apply a redaction to this view hierarchy.
- **unredacted()**: Removes any reason to apply a redaction to this view hierarchy.
- **invalidatableContent(_:)**: Mark the receiver as their content might be invalidated.

## Visibility

- **hidden()**: Hides this view unconditionally.
- **labelsHidden()**: Hides the labels of any controls contained within this view.
- **menuIndicator(_:)**: Sets the menu indicator visibility for controls within this view.
- **listRowSeparator(_:edges:)**: Sets the display mode for the separator associated with this specific row.
- **listSectionSeparator(_:edges:)**: Sets whether to hide the separator associated with a list section.
- **persistentSystemOverlays(_:)**: Sets the preferred visibility of the non-transient system views overlaying the app.
- **scrollIndicators(_:axes:)**: Sets the visibility of scroll indicators within this view.
- **scrollClipDisabled(_:)**: Sets whether a scroll view clips its content to its bounds.
- **tableColumnHeaders(_:)**: Controls the visibility of a `Table`’s column header views.
- **upperLimbVisibility(_:)**: Sets the preferred visibility of the user’s upper limbs, while an [ImmersiveSpace](ImmersiveSpace.zh-Hans.md) scene is presented.
- **volumeBaseplateVisibility(_:)**: Sets the visibility of the baseplate of a volume, which appears when a user looks towards the ‘floor’ of a volume and during resize. Both `automatic` and `visible` will show the baseplate. `hidden` will never show it.

## Sensory feedback

- **sensoryFeedback(_:trigger:)**: Plays the specified `feedback` when the provided `trigger` value changes.
- **sensoryFeedback(trigger:_:)**: Plays feedback when returned from the `feedback` closure after the provided `trigger` value changes.
- **sensoryFeedback(_:trigger:condition:)**: Plays the specified `feedback` when the provided `trigger` value changes and the `condition` closure returns `true`.

## Widget configuration

- **widgetAccentable(_:)**: Adds the view and all of its subviews to the accented group.
- **widgetCurvesContent(_:)**: Displays the widget’s content along a curve if the context allows it.
- **widgetLabel(_:)**: Returns a localized text label that displays additional content outside the accessory family widget’s main SwiftUI view.
- **widgetLabel(label:)**: Creates a label for displaying additional content outside an accessory family widget’s main SwiftUI view.
- **dynamicIsland(verticalPlacement:)**: Specifies the vertical placement for a view of an expanded Live Activity that appears in the Dynamic Island.
- **accessoryWidgetGroupStyle(_:)**: The view modifier that can be applied to `AccessoryWidgetGroup` to specify the shape the three content views will be masked with. The value of `style` is set to `.automatic`, which is `.circular` by default.

## Window behaviors

- **windowDismissBehavior(_:)**: Configures the dismiss functionality for the window enclosing `self`.
- **windowFullScreenBehavior(_:)**: Configures the full screen functionality for the window enclosing `self`.
- **windowMinimizeBehavior(_:)**: Configures the minimize functionality for the window enclosing `self`.
- **windowResizeBehavior(_:)**: Configures the resize functionality for the window enclosing `self`.

## Configuring view elements

- **Accessibility modifiers**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Text and symbol modifiers**: Manage the rendering, selection, and entry of text in your view.
- **Auxiliary view modifiers**: Add and configure supporting views, like toolbars and context menus.
- **Chart view modifiers**: Configure charts that you declare with Swift Charts.

