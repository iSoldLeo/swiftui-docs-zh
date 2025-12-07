---
来源： https://developer.apple.com/documentation/SwiftUI/View-Deprecated
抓取时间： 2025-12-02T17:22:19Z
---

# 过时的修饰词

**API 集合**

查看不支持的修饰符及其替代品。

## 概览

避免在应用程序中使用过时的修饰符。选择一个修饰符，查看应使用的替代修饰符。

### 辅助功能修饰符

- **accessibility(label:)**：为视图添加描述其内容的标签。
- **accessibility(value:)**：为视图包含的值添加文字说明。
- **accessibility(hidden:)**：指定是否从系统辅助功能中隐藏该视图。
- **accessibility(identifier:)**：使用指定的字符串来标识视图。
- **accessibility(selectionIdentifier:)**：为该视图的辅助元素设置选择标识符。
- **accessibility(hint:)**：向用户传达执行视图操作后发生的情况。
- **accessibility(activationPoint:)**：指定视图中发生激活的点。
- **accessibility(inputLabels:)**：设置用户识别视图的备用输入标签。
- **accessibility(addTraits:)**：将给定的特征添加到视图中。
- **accessibility(removeTraits:)**：从该视图中删除给定性状。
- **accessibility(sortPriority:)**：设置该视图的可访问性元素相对于同级元素的排序优先顺序。

### 外观修饰符

- **colorScheme(_:)**：设置此视图的配色方案。
- **listRowPlatterColor(_:)**：设置将此视图放入列表时系统应用于行背景的颜色。
- **background(_:alignment:)**：将给定视图分层到此视图后面。
- **overlay(_:alignment:)**：在此视图前分层显示辅助视图。
- **foregroundColor(_:)**：设置此视图显示的前景元素的颜色。
- **complicationForeground()**：将此视图提升为复杂功能中的前景视图。

## 文本修改器

- **autocapitalization(_:)**：设置是否对该视图应用自动大写。
- **disableAutocorrection(_:)**：设置是否禁用此视图的自动更正功能。

## 辅助视图修改器

- **navigationBarTitle(_:)**：为该视图设置导航栏中的标题。
- **navigationBarTitle(_:displayMode:)**：为该视图设置导航栏中的标题和显示模式。
- **navigationBarItems(leading:)**：设置此视图的导航栏项目。
- **navigationBarItems(leading:trailing:)**：设置此视图的导航栏项目：设置此视图的导航栏项目。
- **navigationBarItems(trailing:)**：为该视图配置导航栏项目。
- **navigationBarHidden(_:)**：隐藏此视图的导航栏。
- **statusBar(hidden:)**：设置状态栏的可见性。
- **contextMenu(_:)**：为视图添加上下文菜单。

## 样式修改器

- **menuButtonStyle(_:)**：设置该视图中菜单按钮的样式。
- **navigationViewStyle(_:)**：设置此视图中导航视图的样式。

## 布局修改器

- **frame()**：将此视图定位在不可见框架内。
- **edgesIgnoringSafeArea(_:)**：将视图的建议区域扩展到屏幕安全区域之外。
- **coordinateSpace(name:)**：为视图的坐标空间指定名称，这样其他代码就可以对相对于命名空间的点和尺寸等维度进行操作。

### 图形和渲染修改器

- **accentColor(_:)**：为该视图及其包含的视图设置强调色。
- **mask(_:)**：使用给定视图的 alpha 通道为该视图添加蒙版。
- **animation(_:)**：将给定的动画应用到此视图中的所有可动画值。
- **cornerRadius(_:antialiased:)**：以指定的边角半径将此视图剪切到其边界帧。

## 输入和事件修改器

- **onChange(of:perform:)**：添加当给定值发生变化时要执行的操作。
- **onTapGesture(count:coordinateSpace:perform:)**：添加当该视图识别到点击手势时要执行的操作，并为该操作提供交互位置。
- **onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)**：添加该视图识别长按手势时要执行的操作。
- **onLongPressGesture(minimumDuration:pressing:perform:)**：添加该视图识别长按手势时要执行的操作。
- **onPasteCommand(of:perform:)**：添加响应系统粘贴命令时要执行的操作。
- **onPasteCommand(of:validator:perform:)**：添加响应系统粘贴命令的操作，其中包含您验证的项目。
- **onDrop(of:delegate:)**：定义拖放操作的目标，其大小和位置与此视图相同，其行为由给定的委托控制。
- **onDrop(of:isTargeted:perform:)**：定义拖放操作的目标，该操作使用您指定的闭包处理拖放的内容。
- **focusable(_:onFocusChange:)**：指定视图是否可聚焦，如果可聚焦，则添加视图聚焦时要执行的操作。
- **onContinuousHover(coordinateSpace:perform:)**：添加指针进入、在视图范围内移动和退出视图时要执行的操作。

### 视图显示修改器

- **actionSheet(isPresented:content:)**：当给定条件为真时，显示操作页。
- **actionSheet(item:content:)**：使用给定项目作为工作表内容的数据源，显示操作工作表。
- **alert(isPresented:content:)**：向用户发出警报。
- **alert(item:content:)**：向用户发出警报。

## 搜索修饰符

- **searchable(text:placement:prompt:suggestions:)**：将此视图标记为可搜索视图，从而配置显示搜索字段。

## 标签修改器

- **tabItem(_:)**：设置与此视图相关联的选项卡栏项。


---
source: https://developer.apple.com/documentation/SwiftUI/View-Deprecated
crawled: 2025-12-02T17:22:19Z
---

# Deprecated modifiers

**API Collection**

Review unsupported modifiers and their replacements.

## Overview

Avoid using deprecated modifiers in your app. Select a modifier to see the replacement that you should use instead.

## Accessibility modifiers

- **accessibility(label:)**: Adds a label to the view that describes its contents.
- **accessibility(value:)**: Adds a textual description of the value that the view contains.
- **accessibility(hidden:)**: Specifies whether to hide this view from system accessibility features.
- **accessibility(identifier:)**: Uses the specified string to identify the view.
- **accessibility(selectionIdentifier:)**: Sets a selection identifier for this view’s accessibility element.
- **accessibility(hint:)**: Communicates to the user what happens after performing the view’s action.
- **accessibility(activationPoint:)**: Specifies the point where activations occur in the view.
- **accessibility(inputLabels:)**: Sets alternate input labels with which users identify a view.
- **accessibility(addTraits:)**: Adds the given traits to the view.
- **accessibility(removeTraits:)**: Removes the given traits from this view.
- **accessibility(sortPriority:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

## Appearance modifiers

- **colorScheme(_:)**: Sets this view’s color scheme.
- **listRowPlatterColor(_:)**: Sets the color that the system applies to the row background when this view is placed in a list.
- **background(_:alignment:)**: Layers the given view behind this view.
- **overlay(_:alignment:)**: Layers a secondary view in front of this view.
- **foregroundColor(_:)**: Sets the color of the foreground elements displayed by this view.
- **complicationForeground()**: Promotes this view to the foreground in a complication.

## Text modifiers

- **autocapitalization(_:)**: Sets whether to apply auto-capitalization to this view.
- **disableAutocorrection(_:)**: Sets whether to disable autocorrection for this view.

## Auxiliary view modifiers

- **navigationBarTitle(_:)**: Sets the title in the navigation bar for this view.
- **navigationBarTitle(_:displayMode:)**: Sets the title and display mode in the navigation bar for this view.
- **navigationBarItems(leading:)**: Sets the navigation bar items for this view.
- **navigationBarItems(leading:trailing:)**: Sets the navigation bar items for this view.
- **navigationBarItems(trailing:)**: Configures the navigation bar items for this view.
- **navigationBarHidden(_:)**: Hides the navigation bar for this view.
- **statusBar(hidden:)**: Sets the visibility of the status bar.
- **contextMenu(_:)**: Adds a context menu to the view.

## Style modifiers

- **menuButtonStyle(_:)**: Sets the style for menu buttons within this view.
- **navigationViewStyle(_:)**: Sets the style for navigation views within this view.

## Layout modifiers

- **frame()**: Positions this view within an invisible frame.
- **edgesIgnoringSafeArea(_:)**: Changes the view’s proposed area to extend outside the screen’s safe areas.
- **coordinateSpace(name:)**: Assigns a name to the view’s coordinate space, so other code can operate on dimensions like points and sizes relative to the named space.

## Graphics and rendering modifiers

- **accentColor(_:)**: Sets the accent color for this view and the views it contains.
- **mask(_:)**: Masks this view using the alpha channel of the given view.
- **animation(_:)**: Applies the given animation to all animatable values within this view.
- **cornerRadius(_:antialiased:)**: Clips this view to its bounding frame, with the specified corner radius.

## Input and events modifiers

- **onChange(of:perform:)**: Adds an action to perform when the given value changes.
- **onTapGesture(count:coordinateSpace:perform:)**: Adds an action to perform when this view recognizes a tap gesture, and provides the action with the location of the interaction.
- **onLongPressGesture(minimumDuration:maximumDistance:pressing:perform:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onLongPressGesture(minimumDuration:pressing:perform:)**: Adds an action to perform when this view recognizes a long press gesture.
- **onPasteCommand(of:perform:)**: Adds an action to perform in response to the system’s Paste command.
- **onPasteCommand(of:validator:perform:)**: Adds an action to perform in response to the system’s Paste command with items that you validate.
- **onDrop(of:delegate:)**: Defines the destination for a drag and drop operation with the same size and position as this view, with behavior controlled by the given delegate.
- **onDrop(of:isTargeted:perform:)**: Defines the destination of a drag-and-drop operation that handles the dropped content with a closure that you specify.
- **focusable(_:onFocusChange:)**: Specifies if the view is focusable and, if so, adds an action to perform when the view comes into focus.
- **onContinuousHover(coordinateSpace:perform:)**: Adds an action to perform when the pointer enters, moves within, and exits the view’s bounds.

## View presentation modifiers

- **actionSheet(isPresented:content:)**: Presents an action sheet when a given condition is true.
- **actionSheet(item:content:)**: Presents an action sheet using the given item as a data source for the sheet’s content.
- **alert(isPresented:content:)**: Presents an alert to the user.
- **alert(item:content:)**: Presents an alert to the user.

## Search modifiers

- **searchable(text:placement:prompt:suggestions:)**: Marks this view as searchable, which configures the display of a search field.

## Tab modifiers

- **tabItem(_:)**: Sets the tab bar item associated with this view.

