---
来源：https://developer.apple.com/documentation/SwiftUI/ShareLink/init(item:subject:message:label:)
抓取时间： 2025-12-03T05:44:59Z


# init(item:subject:message:label:)

**Initializer**

创建一个显示共享界面的实例。

## 声明

```swift
nonisolated init(item: String, subject: Text? = nil, message: Text? = nil, @ViewBuilder label: () -> Label) where Data == CollectionOfOne<String>
```

## 参数

- **item**：要共享的项目。
- **subject**：共享到支持主题字段的活动时要显示的项目标题。
- **message**：项目的描述，在分享到支持信息字段的活动时显示。活动可能支持归属文本或 HTML 字符串。
- **label**：视图创建器，可生成描述共享操作的标签。

## 共享一个项目

- **init(item:subject:message:)**：创建一个显示共享界面的实例。
- **init(_:item:subject:message:)**：创建一个带有自定义标签的实例，用于显示共享界面。


---
source: https://developer.apple.com/documentation/SwiftUI/ShareLink/init(item:subject:message:label:)
crawled: 2025-12-03T05:44:59Z
---

# init(item:subject:message:label:)

**Initializer**

Creates an instance that presents the share interface.

## Declaration

```swift
nonisolated init(item: String, subject: Text? = nil, message: Text? = nil, @ViewBuilder label: () -> Label) where Data == CollectionOfOne<String>
```

## Parameters

- **item**: The item to share.
- **subject**: A title for the item to show when sharing to activities that support a subject field.
- **message**: A description of the item to show when sharing to activities that support a message field. Activities may support attributed text or HTML strings.
- **label**: A view builder that produces a label that describes the share action.

## Sharing an item

- **init(item:subject:message:)**: Creates an instance that presents the share interface.
- **init(_:item:subject:message:)**: Creates an instance, with a custom label, that presents the share interface.

