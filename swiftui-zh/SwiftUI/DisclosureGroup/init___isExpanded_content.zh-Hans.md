---
来源：https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(_:isExpanded:content:)
抓取时间： 2025-12-03T05:41:05Z
---

# init(_:isExpanded:content:)

**Initializer**

创建一个披露组，使用提供的本地化字符串键为标签创建文本视图，并绑定展开状态（展开或折叠）。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isExpanded: Binding<Bool>, @ViewBuilder content: @escaping () -> Content)
```

## 参数

- **titleKey**：描述披露组内容的 `self` 本地化标签的密钥。
- **isExpanded**：与布尔值的绑定，用于确定组的展开状态（展开或折叠）。
- **content**：披露组展开时显示的内容。

## 创建信息披露组

- **init(_:content:)**：创建披露组，使用提供的本地化字符串键为标签创建文本视图。
- **init(content:label:)**：用给定的标签和内容视图创建信息披露组。
- **init(isExpanded:content:label:)**：使用给定的标签和内容视图创建信息公开组，并绑定到展开状态（展开或折叠）。


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(_:isExpanded:content:)
crawled: 2025-12-03T05:41:05Z
---

# init(_:isExpanded:content:)

**Initializer**

Creates a disclosure group, using a provided localized string key to create a text view for the label, and a binding to the expansion state (expanded or collapsed).

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, isExpanded: Binding<Bool>, @ViewBuilder content: @escaping () -> Content)
```

## Parameters

- **titleKey**: The key for the localized label of `self` that describes the content of the disclosure group.
- **isExpanded**: A binding to a Boolean value that determines the group’s expansion state (expanded or collapsed).
- **content**: The content shown when the disclosure group expands.

## Creating a disclosure group

- **init(_:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label.
- **init(content:label:)**: Creates a disclosure group with the given label and content views.
- **init(isExpanded:content:label:)**: Creates a disclosure group with the given label and content views, and a binding to the expansion state (expanded or collapsed).

