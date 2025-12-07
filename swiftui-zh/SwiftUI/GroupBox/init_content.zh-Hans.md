--- 来源：https://developer.apple.com/documentation/SwiftUI/GroupBox/init(content:)

抓取时间：2025-12-03T05:41:57Z

---

# init(content:)

**Initializer**

创建一个未标记的分组框，并指定提供的视图内容。

## 声明

```swift
nonisolated init(@ViewBuilder content: () -> Content)
```

## 参数

- **content**：一个用于生成分组框内容的 [ViewBuilder](../ViewBuilder.zh-Hans.md)。

## 创建分组框

- **init(content:label:)**：创建一个包含提供的标签和视图内容的分组框。

- **init(_:content:)**：创建一个包含提供的视图内容和标题的分组框。


---
source: https://developer.apple.com/documentation/SwiftUI/GroupBox/init(content:)
crawled: 2025-12-03T05:41:57Z
---

# init(content:)

**Initializer**

Creates an unlabeled group box with the provided view content.

## Declaration

```swift
nonisolated init(@ViewBuilder content: () -> Content)
```

## Parameters

- **content**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that produces the content for the group box.

## Creating a group box

- **init(content:label:)**: Creates a group box with the provided label and view content.
- **init(_:content:)**: Creates a group box with the provided view content and title.

