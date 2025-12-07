--- 来源：https://developer.apple.com/documentation/SwiftUI/GroupBox/init(content:label:)

抓取时间：2025-12-01T10:31:08Z

---

# init(content:label:)

**Initializer**

创建一个带有指定标签和视图内容的分组框。

## 声明

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **content**：一个用于生成分组框内容的 [ViewBuilder](../ViewBuilder.zh-Hans.md) 对象。

- **label**：一个用于生成分组框标签的 [ViewBuilder](../ViewBuilder.zh-Hans.md) 对象。

## 创建分组框

- **init(content:)**：创建一个带有指定视图内容的无标签分组框。 - **init(_:content:)**：创建一个包含指定视图内容和标题的分组框。


---
source: https://developer.apple.com/documentation/SwiftUI/GroupBox/init(content:label:)
crawled: 2025-12-01T10:31:08Z
---

# init(content:label:)

**Initializer**

Creates a group box with the provided label and view content.

## Declaration

```swift
init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **content**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that produces the content for the group box.
- **label**: A [ViewBuilder](../ViewBuilder.zh-Hans.md) that produces a label for the group box.

## Creating a group box

- **init(content:)**: Creates an unlabeled group box with the provided view content.
- **init(_:content:)**: Creates a group box with the provided view content and title.

