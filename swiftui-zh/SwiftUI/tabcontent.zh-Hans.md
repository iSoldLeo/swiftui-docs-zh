---
来源： https://developer.apple.com/documentation/swiftui/tabcontent
抓取时间： 2025-12-04T13:08:20Z
---

# 标签内容

**Protocol**

为标签视图中可编程选择的标签提供内容的类型。

## 声明

```swift
@MainActor @preconcurrency protocol TabContent<TabValue>
```

## 概览

如果符合本协议的类型的基本声明中包含了本协议，那么该类型就继承了本协议的 `@preconcurrency @MainActor` 隔离性：

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

默认情况下与主要角色隔离，但这不是必须的。在扩展声明中声明一致性，就可以不使用主要角色隔离：

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## 关联类型

- **Body**：代表此内容类型主体的内容类型。
- **TabValue**：用于驱动包含选项卡视图的选择的类型。

### 实例属性

- **body**：该类型嵌套内容的值。

### 实例方法

- **accessibilityHint(_:isEnabled:)**：向用户传达选择选项卡后发生的情况。
- **accessibilityIdentifier(_:isEnabled:)**：使用您指定的字符串来标识视图。使用此值进行测试。用户看不到它。
- **accessibilityInputLabels(_:isEnabled:)**：设置用户识别选项卡的备用输入标签。
- **accessibilityLabel(_:isEnabled:)**：为标签页添加描述其内容的标签。
- **accessibilityValue(_:isEnabled:)**：为选项卡包含的值添加文字说明。
- **badge(_:)**：从整数值生成标签页的徽章。
- **contextMenu(menuItems:)**：为标签页添加上下文菜单。
- **customizationBehavior(_:for:)**：配置自定义选项卡视图内容的自定义行为。
- **customizationID(_:)**：设置标签页的标识符，以保持其状态。
- **defaultVisibility(_:for:)**：配置标签页在自定义上下文中的默认可见性。
- **disabled(_:)**：控制用户是否可以与该选项卡交互。
- **draggable(_:)**：将此选项卡激活为拖放操作的源。该选项卡只能在侧边栏中拖动。
- **dropDestination(for:action:)**：定义拖放操作的目的地，该操作使用您指定的闭合器处理拖放的内容。
- **hidden(_:)**：向用户隐藏选项卡。
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**：当给定条件为真时显示弹出窗口。
- **popover(item:attachmentAnchor:arrowEdge:content:)**：使用给定项目作为弹出窗口内容的数据源，显示弹出窗口。
- **sectionActions(content:)**：为标签页部分添加自定义操作。
- **springLoadingBehavior(_:)**：设置标签页的弹簧加载行为。
- **swipeActions(edge:allowsFullSwipe:content:)**：为选项卡视图中的选项卡添加自定义轻扫操作。
- **tabPlacement(_:)**：指定标签页的位置。

## 配置标签页

- **sectionActions(content:)**：为部分添加自定义操作。
- **TabPlacement**：标签页可以出现的位置。
- **TabContentBuilder**：结果生成器，用于为支持编程选择的选项卡视图构造选项卡。该创建器要求选项卡视图中的所有选项卡具有相同的选择类型。
- **AnyTabContent**：键入已删除的选项卡内容。

## 符合类型

- AnyTabContent
- 每个
- 组
- 标签
- TabSection


---
source: https://developer.apple.com/documentation/swiftui/tabcontent
crawled: 2025-12-04T13:08:20Z
---

# TabContent

**Protocol**

A type that provides content for programmatically selectable tabs in a tab view.

## Declaration

```swift
@MainActor @preconcurrency protocol TabContent<TabValue>
```

## Overview

A type conforming to this protocol inherits `@preconcurrency @MainActor` isolation from the protocol if the conformance is included in the type’s base declaration:

```swift
struct MyCustomType: Transition {
    // `@preconcurrency @MainActor` isolation by default
}
```

Isolation to the main actor is the default, but it’s not required. Declare the conformance in an extension to opt out of main actor isolation:

```swift
extension MyCustomType: Transition {
    // `nonisolated` by default
}
```

## Associated Types

- **Body**: The type of content representing the body of this content type.
- **TabValue**: The type used to drive selection for the containing tab view.

## Instance Properties

- **body**: The value of this type’s nested content.

## Instance Methods

- **accessibilityHint(_:isEnabled:)**: Communicates to the user what happens after selecting the tab.
- **accessibilityIdentifier(_:isEnabled:)**: Uses the string you specify to identify the view. Use this value for testing. It isn’t visible to the user.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a tab.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the tab that describes its contents.
- **accessibilityValue(_:isEnabled:)**: Adds a textual description of the value that the tab contains.
- **badge(_:)**: Generates a badge for a tab from an integer value.
- **contextMenu(menuItems:)**: Adds a context menu to a tab.
- **customizationBehavior(_:for:)**: Configures the customization behavior of customizable tab view content.
- **customizationID(_:)**: Sets the identifier for a tab to persist its state.
- **defaultVisibility(_:for:)**: Configures the default visibility of a tab in customizable contexts.
- **disabled(_:)**: Controls whether users can interact with this tab.
- **draggable(_:)**: Activates this tab as the source of a drag and drop operation. This tab can only be dragged when in the sidebar.
- **dropDestination(for:action:)**: Defines the destination of a drag and drop operation that handles the dropped content with a closure that you specify.
- **hidden(_:)**: Hides the tab from the user.
- **popover(isPresented:attachmentAnchor:arrowEdge:content:)**: Presents a popover when a given condition is true.
- **popover(item:attachmentAnchor:arrowEdge:content:)**: Presents a popover using the given item as a data source for the popover’s content.
- **sectionActions(content:)**: Adds custom actions to a tab section.
- **springLoadingBehavior(_:)**: Sets the spring loading behavior for the tab.
- **swipeActions(edge:allowsFullSwipe:content:)**: Adds custom swipe actions to a tab in a tab view.
- **tabPlacement(_:)**: Specifies the placement of a tab.

## Configuring a tab

- **sectionActions(content:)**: Adds custom actions to a section.
- **TabPlacement**: A place that a tab can appear.
- **TabContentBuilder**: A result builder that constructs tabs for a tab view that supports programmatic selection. This builder requires that all tabs in the tab view have the same selection type.
- **AnyTabContent**: Type erased tab content.

## Conforming Types

- AnyTabContent
- ForEach
- Group
- Tab
- TabSection

