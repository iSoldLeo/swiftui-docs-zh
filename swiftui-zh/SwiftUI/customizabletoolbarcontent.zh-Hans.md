---
来源： https://developer.apple.com/documentation/swiftui/customizabletoolbarcontent
抓取时间： 2025-12-04T13:08:44Z
---

# 自定义工具栏内容

**Protocol**

符合类型表示可放置在自定义工具栏不同位置的项目。

## 声明

```swift
protocol CustomizableToolbarContent : ToolbarContent where Self.Body : CustomizableToolbarContent
```

## 使用默认选项

- **defaultCustomization()**：使用默认可见性和选项配置自定义工具栏内容。
- **defaultCustomization(_:options:)**：配置具有默认行为的可定制工具栏项目的行为方式。

## 自定义行为

- **customizationBehavior(_:)**：配置自定义工具栏内容的自定义行为。

### 实例方法

- **hidden(_:)**：在工具栏中隐藏工具栏项目。
- **matchedTransitionSource(id:in:)**：将此工具栏内容标识为导航转换（如缩放转换）的来源。
- **sharedBackgroundVisibility(_:)**：控制工具栏中项目的玻璃背景效果的可见性。在某些情况下，例如 iOS 的导航栏和 macOS 的窗口工具栏，工具栏项目将获得与同一逻辑分组中的其他项目共享的玻璃背景效果。

## 填充自定义工具栏

- **toolbar(id:content:)**：用指定的项目填充工具栏或导航栏，允许用户自定义。
- **ToolbarCustomizationBehavior**：自定义工具栏内容的自定义行为。
- **ToolbarCustomizationOptions**：影响可定制工具栏内容默认定制行为的选项。
- **SearchToolbarBehavior**：工具栏中搜索字段的行为。

## 继承自

- 工具栏内容

## 继承类型

- 组
- 工具栏项目
- 工具栏间隔
- 工具栏标题菜单


---
source: https://developer.apple.com/documentation/swiftui/customizabletoolbarcontent
crawled: 2025-12-04T13:08:44Z
---

# CustomizableToolbarContent

**Protocol**

Conforming types represent items that can be placed in various locations in a customizable toolbar.

## Declaration

```swift
protocol CustomizableToolbarContent : ToolbarContent where Self.Body : CustomizableToolbarContent
```

## Using default options

- **defaultCustomization()**: Configures customizable toolbar content with the default visibility and options.
- **defaultCustomization(_:options:)**: Configures the way customizable toolbar items with the default behavior behave.

## Customizing the behavior

- **customizationBehavior(_:)**: Configures the customization behavior of customizable toolbar content.

## Instance Methods

- **hidden(_:)**: Hides a toolbar item within its toolbar.
- **matchedTransitionSource(id:in:)**: Identifies this toolbar content as the source of a navigation transition, such as a zoom transition.
- **sharedBackgroundVisibility(_:)**: Controls the visibility of the glass background effect on items in the toolbar. In certain contexts, such as the navigation bar on iOS and the window toolbar on macOS, toolbar items will be given a glass background effect that is shared with other items in the same logical grouping.

## Populating a customizable toolbar

- **toolbar(id:content:)**: Populates the toolbar or navigation bar with the specified items, allowing for user customization.
- **ToolbarCustomizationBehavior**: The customization behavior of customizable toolbar content.
- **ToolbarCustomizationOptions**: Options that influence the default customization behavior of customizable toolbar content.
- **SearchToolbarBehavior**: The behavior of a search field in a toolbar.

## Inherits From

- ToolbarContent

## Conforming Types

- Group
- ToolbarItem
- ToolbarSpacer
- ToolbarTitleMenu

