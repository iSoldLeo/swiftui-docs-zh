---
来源：https://developer.apple.com/documentation/SwiftUI/ShareLink/init(项目:主题:消息:)
抓取时间： 2025-12-03T05:45:02Z
---

# init(items:subject:message:)

**Initializer**

创建一个显示共享界面的实例。

## 声明

```swift
nonisolated init(items: Data, subject: Text? = nil, message: Text? = nil)
```

## 参数

- **items**：要共享的项目。
- **subject**：共享到支持主题字段的活动时要显示的项目标题。
- **message**：共享到支持信息字段的活动时要显示的项目的说明。活动可能支持归属文本或 HTML 字符串。

### 讨论

如果您想要`ShareLink` 的系统标准外观，请使用此初始化程序。

## 共享项目

- **init(_:items:subject:message:)**：创建一个带有自定义标签的实例，显示共享界面。
- **init(items:subject:message:label:)**：创建显示共享界面的实例。


---
source: https://developer.apple.com/documentation/SwiftUI/ShareLink/init(items:subject:message:)
crawled: 2025-12-03T05:45:02Z
---

# init(items:subject:message:)

**Initializer**

Creates an instance that presents the share interface.

## Declaration

```swift
nonisolated init(items: Data, subject: Text? = nil, message: Text? = nil)
```

## Parameters

- **items**: The items to share.
- **subject**: A title for the items to show when sharing to activities that support a subject field.
- **message**: A description of the items to show when sharing to activities that support a message field. Activities may support attributed text or HTML strings.

## Discussion

Use this initializer when you want the system-standard appearance for `ShareLink`.

## Sharing items

- **init(_:items:subject:message:)**: Creates an instance, with a custom label, that presents the share interface.
- **init(items:subject:message:label:)**: Creates an instance that presents the share interface.

