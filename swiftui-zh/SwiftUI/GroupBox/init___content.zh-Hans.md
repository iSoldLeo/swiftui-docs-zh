--- 来源：https://developer.apple.com/documentation/SwiftUI/GroupBox/init(_:content:)

抓取时间：2025-12-03T05:41:58Z

---

# init(_:content:)

**Initializer**

使用提供的视图内容和标题创建一个分组框。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：分组框标题的键，用于描述分组框的内容。

- **content**：一个 [ViewBuilder](../ViewBuilder.zh-Hans.md)，用于生成分组框的内容。

## 创建分组框

- **init(content:)**：使用提供的视图内容创建一个无标签的分组框。

- **init(content:label:)**：创建一个带有指定标签和视图内容的分组框。


---
source: https://developer.apple.com/documentation/SwiftUI/GroupBox/init(_:content:)
crawled: 2025-12-03T05:41:58Z
---

# init(_:content:)

**Initializer**

Creates a group box with the provided view content and title.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The key for the group box’s title, which describes the content of the group box.
- **content**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that produces the content for the group box.

## Creating a group box

- **init(content:)**: Creates an unlabeled group box with the provided view content.
- **init(content:label:)**: Creates a group box with the provided label and view content.

