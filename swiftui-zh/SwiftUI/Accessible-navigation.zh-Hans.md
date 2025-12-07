---
来源： https://developer.apple.com/documentation/SwiftUI/Accessible-navigation
抓取时间： 2025-12-02T16:49:11Z
---

# 无障碍导航

**API 集合**

让用户可以使用转子导航到特定的用户界面元素。

### 概览

无障碍旋转器是一种快捷方式，可让用户快速导航到用户界面的特定元素，还可选择导航到这些元素中的特定文本范围。



系统会自动为许多可导航的元素提供轮播器，但您也可以为特定目的提供额外的轮播器，或者在系统轮播器不能自动拾取屏幕外元素（如[LazyVStack](LazyVStack.zh-Hans.md)或[List](List.zh-Hans.md)中最下方的元素）时替换系统轮播器。

有关设计指导，请参阅《人机界面指南》无障碍部分中的[doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Navigation]。

## 使用转子

- **accessibilityRotor(_:entries:)**：使用指定的用户可见标签和从内容闭合生成的条目创建无障碍旋转器。
- **accessibilityRotor(_:entries:entryID:entryLabel:)**：使用指定的用户可见标签和条目创建无障碍旋转体。
- **accessibilityRotor(_:entries:entryLabel:)**：使用指定的用户可见标签和条目创建无障碍旋转器。
- **accessibilityRotor(_:textRanges:)**：为每个指定范围创建带有指定用户可见标签和条目的无障碍旋转体。旋转体将附加到当前辅助功能元素上，每个条目将进入该元素的指定范围。

## 创建转子

- **AccessibilityRotorContent**：无障碍转子中的内容。
- **AccessibilityRotorContentBuilder**：用于生成转子条目内容的结果生成器。
- **AccessibilityRotorEntry**：一个结构体，代表无障碍旋转器中的一个条目。

## 替换系统转子

- **AccessibilitySystemRotor**：指定用开发者提供的转子替换系统自动提供的转子的转子。

## 配置转子

- **accessibilityRotorEntry(id:in:)**：定义明确的标识符，将此视图的辅助功能元素与辅助功能旋转体中的条目联系起来。
- **accessibilityLinkedGroup(id:in:)**：链接多个辅助功能元素，以便用户可以快速从一个元素导航到另一个元素，即使这些元素在辅助功能层次结构中彼此并不靠近。
- **accessibilitySortPriority(_:)**：设置该视图的辅助功能元素相对于同级元素的排序优先顺序。

### 辅助功能

- **辅助功能基础**：让每个人（包括残障人士）都能访问您的 SwiftUI 应用程序。
- 无障碍外观**：提高应用程序界面内容的可读性。
- 无障碍控件**：提高应用程序所能执行的操作的可访问性。
- 无障碍描述**：对界面元素进行描述，以帮助人们理解它们所代表的含义。


---
source: https://developer.apple.com/documentation/SwiftUI/Accessible-navigation
crawled: 2025-12-02T16:49:11Z
---

# Accessible navigation

**API Collection**

Enable users to navigate to specific user interface elements using rotors.

## Overview

An accessibility rotor is a shortcut that enables users to quickly navigate to specific elements of the user interface, and, optionally, to specific ranges of text within those elements.



The system automatically provides rotors for many navigable elements, but you can supply additional rotors for specific purposes, or replace system rotors when they don’t automatically pick up off-screen elements, like those far down in a [LazyVStack](LazyVStack.zh-Hans.md) or a [List](List.zh-Hans.md).

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Navigation] in the Accessibility section of the Human Interface Guidelines.

## Working with rotors

- **accessibilityRotor(_:entries:)**: Create an Accessibility Rotor with the specified user-visible label, and entries generated from the content closure.
- **accessibilityRotor(_:entries:entryID:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:entries:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:textRanges:)**: Create an Accessibility Rotor with the specified user-visible label and entries for each of the specified ranges. The Rotor will be attached to the current Accessibility element, and each entry will go the specified range of that element.

## Creating rotors

- **AccessibilityRotorContent**: Content within an accessibility rotor.
- **AccessibilityRotorContentBuilder**: Result builder you use to generate rotor entry content.
- **AccessibilityRotorEntry**: A struct representing an entry in an Accessibility Rotor.

## Replacing system rotors

- **AccessibilitySystemRotor**: Designates a Rotor that replaces one of the automatic, system-provided Rotors with a developer-provided Rotor.

## Configuring rotors

- **accessibilityRotorEntry(id:in:)**: Defines an explicit identifier tying an Accessibility element for this view to an entry in an Accessibility Rotor.
- **accessibilityLinkedGroup(id:in:)**: Links multiple accessibility elements so that the user can quickly navigate from one element to another, even when the elements are not near each other in the accessibility hierarchy.
- **accessibilitySortPriority(_:)**: Sets the sort priority order for this view’s accessibility element, relative to other elements at the same level.

## Accessibility

- **Accessibility fundamentals**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Accessible appearance**: Enhance the legibility of content in your app’s interface.
- **Accessible controls**: Improve access to actions that your app can undertake.
- **Accessible descriptions**: Describe interface elements to help people understand what they represent.

