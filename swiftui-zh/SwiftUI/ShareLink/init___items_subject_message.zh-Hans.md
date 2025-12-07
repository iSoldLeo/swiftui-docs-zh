---
来源：https://developer.apple.com/documentation/SwiftUI/ShareLink/init(_:项目:主题:消息:)
抓取时间： 2025-12-03T05:45:03Z


# init(_:items:subject:message:)

**Initializer**

创建一个带有自定义标签的实例，用于显示共享界面。

## 声明

```swift
nonisolated init(_ title: Text, items: Data, subject: Text? = nil, message: Text? = nil)
```

## 参数

- **title**：共享操作的标题。
- **items**：要共享的项目。
- **subject**：共享到支持主题字段的活动时要显示的项目标题。
- **message**：共享到支持信息字段的活动时要显示的项目的说明。活动可能支持归属文本或 HTML 字符串。

## 共享项目

- **init(items:subject:message:)**：创建一个显示共享界面的实例。
- **init(items:subject:message:label:)**：创建显示共享接口的实例。


---
source: https://developer.apple.com/documentation/SwiftUI/ShareLink/init(_:items:subject:message:)
crawled: 2025-12-03T05:45:03Z
---

# init(_:items:subject:message:)

**Initializer**

Creates an instance, with a custom label, that presents the share interface.

## Declaration

```swift
nonisolated init(_ title: Text, items: Data, subject: Text? = nil, message: Text? = nil)
```

## Parameters

- **title**: The title of the share action.
- **items**: The items to share.
- **subject**: A title for the items to show when sharing to activities that support a subject field.
- **message**: A description of the items to show when sharing to activities that support a message field. Activities may support attributed text or HTML strings.

## Sharing items

- **init(items:subject:message:)**: Creates an instance that presents the share interface.
- **init(items:subject:message:label:)**: Creates an instance that presents the share interface.

