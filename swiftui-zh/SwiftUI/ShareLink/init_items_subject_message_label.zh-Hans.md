---
来源：https://developer.apple.com/documentation/SwiftUI/ShareLink/init(项目：主题：消息：标签：)
抓取时间：2025-12-01T10:34:16Z


# init(items:subject:message:label:)

**Initializer**

创建一个显示共享界面的实例。

## 声明

```swift
nonisolated init(items: Data, subject: Text? = nil, message: Text? = nil, @ViewBuilder label: () -> Label)
```

## 参数

- **items**：要共享的项目。
- **subject**：共享到支持主题字段的活动时要显示的项目标题。
- **message**：共享到支持信息字段的活动时要显示的项目的说明。活动可能支持归属文本或 HTML 字符串。
- **label**：视图创建器，可生成描述共享操作的标签。

## 共享项目

- **init(items:subject:message:)**：创建一个显示共享界面的实例。
- **init(_:items:subject:message:)**：创建一个带有自定义标签的实例，用于显示共享界面。


---
source: https://developer.apple.com/documentation/SwiftUI/ShareLink/init(items:subject:message:label:)
crawled: 2025-12-01T10:34:16Z
---

# init(items:subject:message:label:)

**Initializer**

Creates an instance that presents the share interface.

## Declaration

```swift
nonisolated init(items: Data, subject: Text? = nil, message: Text? = nil, @ViewBuilder label: () -> Label)
```

## Parameters

- **items**: The items to share.
- **subject**: A title for the items to show when sharing to activities that support a subject field.
- **message**: A description of the items to show when sharing to activities that support a message field. Activities may support attributed text or HTML strings.
- **label**: A view builder that produces a label that describes the share action.

## Sharing items

- **init(items:subject:message:)**: Creates an instance that presents the share interface.
- **init(_:items:subject:message:)**: Creates an instance, with a custom label, that presents the share interface.

