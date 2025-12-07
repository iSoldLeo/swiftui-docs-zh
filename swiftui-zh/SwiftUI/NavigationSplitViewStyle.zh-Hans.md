---
来源： https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle
抓取时间： 2025-12-02T17:33:26Z
---

# 导航分割视图样式

**Protocol**

指定视图层次结构中导航分割视图的外观和交互的类型。

### 声明

```swift
@MainActor @preconcurrency protocol NavigationSplitViewStyle
```

## 概览

要为视图层次结构配置导航分割视图样式，请使用 [navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md) 修改器。

如果符合该协议的类型的基本声明中包含了该协议，则该类型将继承该协议的 `@preconcurrency @MainActor`隔离：

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

## 创建内置样式

- **automatic**：根据当前上下文自动调整外观的导航分割样式。
- **balanced**：一种导航拆分样式，可缩小详细内容的大小，以便在显示前导列时腾出空间。
- **prominentDetail**：一种导航分割样式，在隐藏或显示前导列时，会尝试保持详细内容的大小。

### 创建自定义样式

- **makeBody(configuration:)**：创建表示导航拆分视图主体的视图。
- **NavigationSplitViewStyle.Configuration**：导航拆分视图实例的属性。
- **Body**：导航拆分视图实例的属性：表示导航拆分视图主体的视图。

## 支持类型

- **AutomaticNavigationSplitViewStyle**：导航分割样式，可根据当前上下文自动调整外观。
- **BalancedNavigationSplitViewStyle**：一种导航拆分样式，可缩小详细内容的大小，以便在显示前导列时腾出空间。
- **ProminentDetailNavigationSplitViewStyle**：一种导航分割样式，在隐藏或显示前导列时尝试保持详细内容的大小。
- **NavigationSplitViewStyleConfiguration**：导航分割视图实例的属性。

## 导航视图的样式

- **navigationSplitViewStyle(_:)**：设置该视图中导航分割视图的样式。
- **tabViewStyle(_:)**：为当前环境中的选项卡视图设置样式。
- **TabViewStyle**：标签视图的外观和交互规范。

## 符合类型

- 自动导航分隔视图样式（AutomaticNavigationSplitViewStyle
- 平衡导航拆分视图样式（BalancedNavigationSplitViewStyle
- 突出细节导航分视图样式


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle
crawled: 2025-12-02T17:33:26Z
---

# NavigationSplitViewStyle

**Protocol**

A type that specifies the appearance and interaction of navigation split views within a view hierarchy.

## Declaration

```swift
@MainActor @preconcurrency protocol NavigationSplitViewStyle
```

## Overview

To configure the navigation split view style for a view hierarchy, use the [navigationSplitViewStyle(_:)](View/navigationSplitViewStyle.zh-Hans.md) modifier.

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

## Creating built-in styles

- **automatic**: A navigation split style that resolves its appearance automatically based on the current context.
- **balanced**: A navigation split style that reduces the size of the detail content to make room when showing the leading column or columns.
- **prominentDetail**: A navigation split style that attempts to maintain the size of the detail content when hiding or showing the leading columns.

## Creating custom styles

- **makeBody(configuration:)**: Creates a view that represents the body of a navigation split view.
- **NavigationSplitViewStyle.Configuration**: The properties of a navigation split view instance.
- **Body**: A view that represents the body of a navigation split view.

## Supporting types

- **AutomaticNavigationSplitViewStyle**: A navigation split style that resolves its appearance automatically based on the current context.
- **BalancedNavigationSplitViewStyle**: A navigation split style that reduces the size of the detail content to make room when showing the leading column or columns.
- **ProminentDetailNavigationSplitViewStyle**: A navigation split style that attempts to maintain the size of the detail content when hiding or showing the leading columns.
- **NavigationSplitViewStyleConfiguration**: The properties of a navigation split view instance.

## Styling navigation views

- **navigationSplitViewStyle(_:)**: Sets the style for navigation split views within this view.
- **tabViewStyle(_:)**: Sets the style for the tab view within the current environment.
- **TabViewStyle**: A specification for the appearance and interaction of a tab view.

## Conforming Types

- AutomaticNavigationSplitViewStyle
- BalancedNavigationSplitViewStyle
- ProminentDetailNavigationSplitViewStyle

