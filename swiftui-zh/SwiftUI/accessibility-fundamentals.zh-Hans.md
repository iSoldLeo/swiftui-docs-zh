--- 来源：https://developer.apple.com/documentation/swiftui/accessibility-fundamentals

抓取时间：2025-12-02T16:01:44Z

---

# 无障碍基础知识

**API 集合**

让您的 SwiftUI 应用对所有人（包括残障人士）都易于使用。

## 概述

与所有 Apple UI 框架一样，SwiftUI 内置了无障碍支持。该框架会检查导航视图、列表、文本字段、滑块、按钮等常用元素，并默认提供基本的无障碍标签和值。您无需进行任何额外操作即可启用这些标准无障碍功能。

SwiftUI 还提供了一些工具来帮助您增强应用的无障碍性。要了解您需要哪些增强功能，请尝试使用 VoiceOver、语音控制和切换控制等无障碍功能，或者向经常使用这些功能的用户收集反馈。然后使用 SwiftUI 提供的辅助功能视图修饰符来改善用户体验。例如，您可以使用 [accessibilityLabel(_:)](View/accessibilityLabel.zh-Hans.md) 或 [accessibilityValue(_:)](View/accessibilityValue.zh-Hans.md) 视图修饰符，显式地为 UI 元素添加辅助功能标签。

针对应用运行的所有平台，自定义辅助功能修饰符的使用。例如，您可能需要调整与 iOS 应用共享同一代码库的配套 Apple Watch 应用的辅助功能元素。如果您在 SwiftUI 中集成了 AppKit 或 UIKit 控件，请公开所有辅助功能标签，并使其可从 [NSViewRepresentable](NSViewRepresentable.zh-Hans.md) 或 [UIViewRepresentable](UIViewRepresentable.zh-Hans.md) 视图访问；或者，如果底层辅助功能标签不可用，则提供自定义辅助功能信息。

有关设计指南，请参阅《人机界面指南》中的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility]。

## 基本功能

- **创建无障碍视图**：通过为 SwiftUI 视图应用无障碍修饰符，让您的应用对所有人无障碍。

## 创建无障碍元素

- **accessibilityElement(children:)**：创建一个新的无障碍元素，或修改现有无障碍元素的 [AccessibilityChildBehavior](AccessibilityChildBehavior.zh-Hans.md)。

- **accessibilityChildren(children:)**：将现有无障碍元素的子元素替换为一个或多个新的合成无障碍元素。

- **accessibilityRepresentation(representation:)**：将此视图的一个或多个无障碍元素替换为新的无障碍元素。

- **AccessibilityChildBehavior**：定义新父元素的子元素的行为。

## 标识元素

- **accessibilityIdentifier(_:)**：使用您指定的字符串来标识视图。

- **accessibilityIdentifier(_:isEnabled:)**：使用您指定的字符串来标识视图。

## 隐藏元素

- **accessibilityHidden(_:)**：指定是否从系统辅助功能中隐藏此视图。

- **accessibilityHidden(_:isEnabled:)**：指定是否从系统辅助功能中隐藏此视图。

## 支持的类型

- **AccessibilityTechnologies**：系统可用的辅助技术。

- **AccessibilityAttachmentModifier**：视图修饰符，用于向视图添加辅助功能属性。

## 辅助功能

- **辅助功能外观**：增强应用界面内容的易读性。

- **辅助功能控件**：改进对应用可执行操作的访问。

- **辅助功能描述**：描述界面元素，帮助用户理解其含义。

- **辅助导航**：使用户能够通过旋转按钮导航至特定的用户界面元素。


---
source: https://developer.apple.com/documentation/swiftui/accessibility-fundamentals
crawled: 2025-12-02T16:01:44Z
---

# Accessibility fundamentals

**API Collection**

Make your SwiftUI apps accessible to everyone, including people with disabilities.

## Overview

Like all Apple UI frameworks, SwiftUI comes with built-in accessibility support. The framework introspects common elements like navigation views, lists, text fields, sliders, buttons, and so on, and provides basic accessibility labels and values by default. You don’t have to do any extra work to enable these standard accessibility features.



SwiftUI also provides tools to help you enhance the accessibility of your app. To find out what enhancements you need, try using your app with accessibility features like VoiceOver, Voice Control, and Switch Control, or get feedback from users of your app that regularly use these features. Then use the accessibility view modifiers that SwiftUI provides to improve the experience. For example, you can explicitly add accessibility labels to elements in your UI using the [accessibilityLabel(_:)](View/accessibilityLabel.zh-Hans.md) or the [accessibilityValue(_:)](View/accessibilityValue.zh-Hans.md) view modifier.

Customize your use of accessibility modifiers for all the platforms that your app runs on. For example, you may need to adjust the accessibility elements for a companion Apple Watch app that shares a common code base with an iOS app. If you integrate AppKit or UIKit controls in SwiftUI, expose any accessibility labels and make them accessible from your [NSViewRepresentable](NSViewRepresentable.zh-Hans.md) or [UIViewRepresentable](UIViewRepresentable.zh-Hans.md) views, or provide custom accessibility information if the underlying accessibility labels aren’t available.

For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility] in the Human Interface Guidelines.

## Essentials

- **Creating accessible views**: Make your app accessible to everyone by applying accessibility modifiers to your SwiftUI views.

## Creating accessible elements

- **accessibilityElement(children:)**: Creates a new accessibility element, or modifies the [AccessibilityChildBehavior](AccessibilityChildBehavior.zh-Hans.md) of the existing accessibility element.
- **accessibilityChildren(children:)**: Replaces the existing accessibility element’s children with one or more new synthetic accessibility elements.
- **accessibilityRepresentation(representation:)**: Replaces one or more accessibility elements for this view with new accessibility elements.
- **AccessibilityChildBehavior**: Defines the behavior for the child elements of the new parent element.

## Identifying elements

- **accessibilityIdentifier(_:)**: Uses the string you specify to identify the view.
- **accessibilityIdentifier(_:isEnabled:)**: Uses the string you specify to identify the view.

## Hiding elements

- **accessibilityHidden(_:)**: Specifies whether to hide this view from system accessibility features.
- **accessibilityHidden(_:isEnabled:)**: Specifies whether to hide this view from system accessibility features.

## Supporting types

- **AccessibilityTechnologies**: Accessibility technologies available to the system.
- **AccessibilityAttachmentModifier**: A view modifier that adds accessibility properties to the view

## Accessibility

- **Accessible appearance**: Enhance the legibility of content in your app’s interface.
- **Accessible controls**: Improve access to actions that your app can undertake.
- **Accessible descriptions**: Describe interface elements to help people understand what they represent.
- **Accessible navigation**: Enable users to navigate to specific user interface elements using rotors.

