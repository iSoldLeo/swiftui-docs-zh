--- 来源：https://developer.apple.com/documentation/SwiftUI/Accessible-descriptions

抓取时间：2025-12-02T16:49:10Z

---

# 辅助功能描述

**API 集合**

描述界面元素，帮助用户理解其含义。

## 概述

SwiftUI 通常可以推断出一些关于用户界面元素的信息，但您可以使用辅助功能修饰符为有需要的用户提供更多信息。

有关设计指南，请参阅《人机界面指南》辅助功能部分的 [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Content-descriptions]。

## 应用标签

- **accessibilityLabel(_:)**：向视图添加描述其内容的标签。

- **accessibilityLabel(_:isEnabled:)**：向视图添加描述其内容的标签。

- **accessibilityLabel(content:)**：为视图添加描述其内容的标签。

- **accessibilityInputLabels(_:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityInputLabels(_:isEnabled:)**：设置用户用于识别视图的备用输入标签。

- **accessibilityLabeledPair(role:id:in:)**：将表示标签的辅助功能元素与匹配内容的元素配对。

- **AccessibilityLabeledPairRole**：辅助功能元素在标签/内容对中的作用。

## 描述值

- **accessibilityValue(_:)**：添加视图包含的值的文本描述。

- **accessibilityValue(_:isEnabled:)**：添加视图包含的值的文本描述。

## 描述内容

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。

- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。

- **AccessibilityHeadingLevel**：标题与其他标题的层级关系。

- **AccessibilityTextContentType**：辅助技术可用于改善语音文本呈现的文本上下文。

## 描述图表

- **accessibilityChartDescriptor(_:)**：向表示图表的视图添加描述符，使所有用户都能访问图表内容。

- **AXChartDescriptorRepresentable**：用于生成 `AXChartDescriptor` 对象的类型，您可以使用该对象提供有关图表及其数据的信息，以便在 VoiceOver 或其他辅助技术中获得无障碍体验。

## 添加自定义描述

- **accessibilityCustomContent(_:_:importance:)**：向视图添加额外的辅助功能信息。

- **AccessibilityCustomContentKey**：用于指定与额外辅助功能信息条目关联的标识符和标签的键。

## 为内容分配特性

- **accessibilityAddTraits(_:)**：向视图添加指定的特性。

- **accessibilityRemoveTraits(_:)**：从该视图中移除指定的特性。

- **AccessibilityTraits**：一组描述元素行为的辅助功能特性。

## 提供提示

- **accessibilityHint(_:)**：向用户说明执行视图操作后会发生什么。

- **accessibilityHint(_:isEnabled:)**：向用户说明执行视图操作后会发生什么。

## 配置 VoiceOver

- **speechAdjustedPitch(_:)**：提高或降低语音文本的音调。

- **speechAlwaysIncludesPunctuation(_:)**：设置 VoiceOver 是否始终朗读文本视图中的所有标点符号。

- **speechAnnouncementsQueued(_:)**：控制是否将待处理的语音提示排队到现有语音之后，而不是打断正在进行的语音。

- **speechSpellsOutCharacters(_:)**：设置 VoiceOver 是否逐字符朗读文本视图的内容。

## 辅助功能

- **辅助功能基础**：让您的 SwiftUI 应用对所有人（包括残障人士）都易于使用。

- **辅助功能外观**：增强应用界面内容的易读性。

- **辅助功能控件**：改进对应用可执行操作的访问。

- **辅助功能导航**：使用户能够使用旋转器导航到特定的用户界面元素。


---
source: https://developer.apple.com/documentation/SwiftUI/Accessible-descriptions
crawled: 2025-12-02T16:49:10Z
---

# Accessible descriptions

**API Collection**

Describe interface elements to help people understand what they represent.

## Overview

SwiftUI can often infer some information about your user interface elements, but you can use accessibility modifiers to provide even more information for users that need it.



For design guidance, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/accessibility#Content-descriptions] in the Accessibility section of the Human Interface Guidelines.

## Applying labels

- **accessibilityLabel(_:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(_:isEnabled:)**: Adds a label to the view that describes its contents.
- **accessibilityLabel(content:)**: Adds a label to the view that describes its contents.
- **accessibilityInputLabels(_:)**: Sets alternate input labels with which users identify a view.
- **accessibilityInputLabels(_:isEnabled:)**: Sets alternate input labels with which users identify a view.
- **accessibilityLabeledPair(role:id:in:)**: Pairs an accessibility element representing a label with the element for the matching content.
- **AccessibilityLabeledPairRole**: The role of an accessibility element in a label / content pair.

## Describing values

- **accessibilityValue(_:)**: Adds a textual description of the value that the view contains.
- **accessibilityValue(_:isEnabled:)**: Adds a textual description of the value that the view contains.

## Describing content

- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.
- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.
- **AccessibilityHeadingLevel**: The hierarchy of a heading in relation to other headings.
- **AccessibilityTextContentType**: Textual context that assistive technologies can use to improve the presentation of spoken text.

## Describing charts

- **accessibilityChartDescriptor(_:)**: Adds a descriptor to a View that represents a chart to make the chart’s contents accessible to all users.
- **AXChartDescriptorRepresentable**: A type to generate an `AXChartDescriptor` object that you use to provide information about a chart and its data for an accessible experience in VoiceOver or other assistive technologies.

## Adding custom descriptions

- **accessibilityCustomContent(_:_:importance:)**: Add additional accessibility information to the view.
- **AccessibilityCustomContentKey**: Key used to specify the identifier and label associated with an entry of additional accessibility information.

## Assigning traits to content

- **accessibilityAddTraits(_:)**: Adds the given traits to the view.
- **accessibilityRemoveTraits(_:)**: Removes the given traits from this view.
- **AccessibilityTraits**: A set of accessibility traits that describe how an element behaves.

## Offering hints

- **accessibilityHint(_:)**: Communicates to the user what happens after performing the view’s action.
- **accessibilityHint(_:isEnabled:)**: Communicates to the user what happens after performing the view’s action.

## Configuring VoiceOver

- **speechAdjustedPitch(_:)**: Raises or lowers the pitch of spoken text.
- **speechAlwaysIncludesPunctuation(_:)**: Sets whether VoiceOver should always speak all punctuation in the text view.
- **speechAnnouncementsQueued(_:)**: Controls whether to queue pending announcements behind existing speech rather than interrupting speech in progress.
- **speechSpellsOutCharacters(_:)**: Sets whether VoiceOver should speak the contents of the text view character by character.

## Accessibility

- **Accessibility fundamentals**: Make your SwiftUI apps accessible to everyone, including people with disabilities.
- **Accessible appearance**: Enhance the legibility of content in your app’s interface.
- **Accessible controls**: Improve access to actions that your app can undertake.
- **Accessible navigation**: Enable users to navigate to specific user interface elements using rotors.

