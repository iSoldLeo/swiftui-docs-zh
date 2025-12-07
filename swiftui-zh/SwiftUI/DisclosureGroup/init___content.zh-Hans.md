---
来源： https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(_:content:)
抓取时间： 2025-12-01T10:30:12Z
---

# init(_:content:)

**Initializer**

创建披露组，使用提供的本地化字符串键为标签创建文本视图。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: @escaping () -> Content)
```

## 参数

- **titleKey**：描述信息披露组内容的 `self` 本地化标签的密钥。
- **content**：信息公开组展开时显示的内容。

## 创建信息公开组

- **init(content:label:)**：用给定的标签和内容视图创建一个信息披露组。
- **init(_:isExpanded:content:)**：使用提供的本地化字符串键为标签创建文本视图，并绑定到展开状态（展开或折叠），从而创建信息披露组。
- **init(isExpanded:content:label:)**：用给定的标签和内容视图创建一个披露组，并绑定到展开状态（展开或折叠）。


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(_:content:)
crawled: 2025-12-01T10:30:12Z
---

# init(_:content:)

**Initializer**

Creates a disclosure group, using a provided localized string key to create a text view for the label.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: @escaping () -> Content)
```

## Parameters

- **titleKey**: The key for the localized label of `self` that describes the content of the disclosure group.
- **content**: The content shown when the disclosure group expands.

## Creating a disclosure group

- **init(content:label:)**: Creates a disclosure group with the given label and content views.
- **init(_:isExpanded:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label, and a binding to the expansion state (expanded or collapsed).
- **init(isExpanded:content:label:)**: Creates a disclosure group with the given label and content views, and a binding to the expansion state (expanded or collapsed).

