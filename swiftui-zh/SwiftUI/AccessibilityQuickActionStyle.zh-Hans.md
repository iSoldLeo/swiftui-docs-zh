--- 来源：https://developer.apple.com/documentation/SwiftUI/AccessibilityQuickActionStyle
抓取时间：2025-12-02T17:43:58Z

---

# AccessibilityQuickActionStyle

**Protocol**

描述辅助功能快捷操作的呈现样式的类型。

## 声明

```swift
protocol AccessibilityQuickActionStyle
```

## 获取内置菜单样式

- **outline**：当辅助功能快捷操作激活时，在视图周围添加动画轮廓的呈现样式。

- **prompt**：当辅助功能快捷操作激活时，向用户显示提示的呈现样式。

## 支持的类型

- **AccessibilityQuickActionOutlineStyle**：当辅助功能快捷操作激活时，向用户显示提示的呈现样式。

- **AccessibilityQuickActionPromptStyle**：一种显示样式，用于在辅助功能快捷操作激活时向用户显示提示。

## 为用户提供快捷操作

- **accessibilityQuickAction(style:content:)**：添加一个快捷操作，当该操作激活时，系统会显示该操作。

- **accessibilityQuickAction(style:isActive:content:)**：添加一个快捷操作，当该操作激活时，系统会显示该操作。

## 符合规范的类型

- AccessibilityQuickActionOutlineStyle

- AccessibilityQuickActionPromptStyle


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityQuickActionStyle
crawled: 2025-12-02T17:43:58Z
---

# AccessibilityQuickActionStyle

**Protocol**

A type that describes the presentation style of an accessibility quick action.

## Declaration

```swift
protocol AccessibilityQuickActionStyle
```

## Getting built-in menu styles

- **outline**: A presentation style that animates an outline around the view when the accessibility quick action is active.
- **prompt**: A presentation style that displays a prompt to the user when the accessibility quick action is active.

## Supporting types

- **AccessibilityQuickActionOutlineStyle**: A presentation style that displays a prompt to the user when the accessibility quick action is active.
- **AccessibilityQuickActionPromptStyle**: A presentation style that displays a prompt to the user when the accessibility quick action is active.

## Offering Quick Actions to people

- **accessibilityQuickAction(style:content:)**: Adds a quick action to be shown by the system when active.
- **accessibilityQuickAction(style:isActive:content:)**: Adds a quick action to be shown by the system when active.

## Conforming Types

- AccessibilityQuickActionOutlineStyle
- AccessibilityQuickActionPromptStyle

