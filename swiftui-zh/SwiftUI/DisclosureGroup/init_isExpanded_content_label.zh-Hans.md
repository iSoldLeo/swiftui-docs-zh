---
来源：https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(isExpanded:content:label:)
抓取时间：2025-12-01T10:30:15Z
---

# init(isExpanded:content:label:)

**Initializer**

使用给定的标签和内容视图创建一个披露组，并绑定到展开状态（展开或折叠）。

### 声明

```swift
init(isExpanded: Binding<Bool>, @ViewBuilder content: @escaping () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **isExpanded**：与布尔值的绑定，布尔值决定分组的展开状态（展开或折叠）。
- **content**：披露组展开时显示的内容。
- **label**：描述信息公开组内容的视图。

## 创建信息公开组

- **init(_:content:)**：创建信息披露组，使用提供的本地化字符串键为标签创建文本视图。
- **init(content:label:)**：用给定的标签和内容视图创建信息披露组。
- **init(_:isExpanded:content:)**：使用提供的本地化字符串键为标签创建文本视图，并绑定到展开状态（展开或折叠），从而创建信息披露组。


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(isExpanded:content:label:)
crawled: 2025-12-01T10:30:15Z
---

# init(isExpanded:content:label:)

**Initializer**

Creates a disclosure group with the given label and content views, and a binding to the expansion state (expanded or collapsed).

## Declaration

```swift
init(isExpanded: Binding<Bool>, @ViewBuilder content: @escaping () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **isExpanded**: A binding to a Boolean value that determines the group’s expansion state (expanded or collapsed).
- **content**: The content shown when the disclosure group expands.
- **label**: A view that describes the content of the disclosure group.

## Creating a disclosure group

- **init(_:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label.
- **init(content:label:)**: Creates a disclosure group with the given label and content views.
- **init(_:isExpanded:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label, and a binding to the expansion state (expanded or collapsed).

