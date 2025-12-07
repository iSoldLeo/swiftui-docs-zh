---
来源：https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(内容：标签：)
抓取时间： 2025-12-03T05:41:04Z
---

# init(content:label:)

**Initializer**

使用给定的标签和内容视图创建一个披露组。

### 声明

```swift
init(@ViewBuilder content: @escaping () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **content**：显示组展开时显示的内容。
- **label**：描述信息公开组内容的视图。

## 创建信息公开组

- **init(_:content:)**：创建信息披露组，使用提供的本地化字符串键为标签创建文本视图。
- **init(_:isExpanded:content:)**：使用提供的本地化字符串键为标签创建文本视图，并绑定到展开状态（展开或折叠），从而创建信息披露组。
- **init(isExpanded:content:label:)**：用给定的标签和内容视图创建一个披露组，并绑定到展开状态（展开或折叠）。


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureGroup/init(content:label:)
crawled: 2025-12-03T05:41:04Z
---

# init(content:label:)

**Initializer**

Creates a disclosure group with the given label and content views.

## Declaration

```swift
init(@ViewBuilder content: @escaping () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **content**: The content shown when the disclosure group expands.
- **label**: A view that describes the content of the disclosure group.

## Creating a disclosure group

- **init(_:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label.
- **init(_:isExpanded:content:)**: Creates a disclosure group, using a provided localized string key to create a text view for the label, and a binding to the expansion state (expanded or collapsed).
- **init(isExpanded:content:label:)**: Creates a disclosure group with the given label and content views, and a binding to the expansion state (expanded or collapsed).

