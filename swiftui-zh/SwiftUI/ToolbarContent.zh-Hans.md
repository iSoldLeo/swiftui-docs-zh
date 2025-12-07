---
来源： https://developer.apple.com/documentation/SwiftUI/ToolbarContent
抓取时间： 2025-12-02T17:31:06Z
---

# 工具栏内容

**Protocol**

符合类型表示可放置在工具栏不同位置的项目。

## 声明

```swift
@MainActor @preconcurrency protocol ToolbarContent
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

## 实现工具栏内容

- **body**：构成工具栏内容的内容组成。
- **Body**：表示该工具栏内容主体的内容类型。

### 实例方法

- **hidden(_:)**：隐藏工具栏中的工具栏项。
- **matchedTransitionSource(id:in:)**：将此工具栏内容标识为导航转换（如缩放转换）的来源。
- **sharedBackgroundVisibility(_:)**：控制工具栏中项目的玻璃背景效果的可见性。在某些情况下，例如 iOS 的导航栏和 macOS 的窗口工具栏，工具栏项目将获得与同一逻辑分组中的其他项目共享的玻璃背景效果。

## 填充工具栏

- **toolbar(content:)**：用指定的项目填充工具栏或导航栏。
- **ToolbarItem**：表示可放置在工具栏或导航栏中的项目的模型。
- **ToolbarItemGroup**：表示一组`ToolbarItem`的模型，可放置在工具栏或导航栏中。
- **ToolbarItemPlacement**：定义工具栏项目位置的结构。
- **ToolbarContentBuilder**：用多表达式闭包构造工具栏项目集。
- **ToolbarSpacer**：工具栏中的标准空格项。
- **DefaultToolbarItem**：工具栏中的标准空格项：表示系统组件的工具栏项目。

## 继承自

- 自定义工具栏内容

## 符合类型

- 默认工具栏项目
- 组
- 工具栏项目
- 工具栏项目组
- 工具栏间隔
- 工具栏标题菜单


---
source: https://developer.apple.com/documentation/SwiftUI/ToolbarContent
crawled: 2025-12-02T17:31:06Z
---

# ToolbarContent

**Protocol**

Conforming types represent items that can be placed in various locations in a toolbar.

## Declaration

```swift
@MainActor @preconcurrency protocol ToolbarContent
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

## Implementing toolbar content

- **body**: The composition of content that comprise the toolbar content.
- **Body**: The type of content representing the body of this toolbar content.

## Instance Methods

- **hidden(_:)**: Hides a toolbar item within its toolbar.
- **matchedTransitionSource(id:in:)**: Identifies this toolbar content as the source of a navigation transition, such as a zoom transition.
- **sharedBackgroundVisibility(_:)**: Controls the visibility of the glass background effect on items in the toolbar. In certain contexts, such as the navigation bar on iOS and the window toolbar on macOS, toolbar items will be given a glass background effect that is shared with other items in the same logical grouping.

## Populating a toolbar

- **toolbar(content:)**: Populates the toolbar or navigation bar with the specified items.
- **ToolbarItem**: A model that represents an item which can be placed in the toolbar or navigation bar.
- **ToolbarItemGroup**: A model that represents a group of `ToolbarItem`s which can be placed in the toolbar or navigation bar.
- **ToolbarItemPlacement**: A structure that defines the placement of a toolbar item.
- **ToolbarContentBuilder**: Constructs a toolbar item set from multi-expression closures.
- **ToolbarSpacer**: A standard space item in toolbars.
- **DefaultToolbarItem**: A toolbar item that represents a system component.

## Inherited By

- CustomizableToolbarContent

## Conforming Types

- DefaultToolbarItem
- Group
- ToolbarItem
- ToolbarItemGroup
- ToolbarSpacer
- ToolbarTitleMenu

