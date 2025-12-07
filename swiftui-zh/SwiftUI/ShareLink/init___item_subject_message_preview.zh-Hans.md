---
来源：https://developer.apple.com/documentation/SwiftUI/ShareLink/init(_:项目:主题:消息:预览:)
抓取时间：2025-12-01T10:34:13Z


# init(_:item:subject:message:preview:)

**Initializer**

创建一个带有自定义标签的实例，用于显示共享界面。

## 声明

```swift
nonisolated init<I>(_ title: Text, item: I, subject: Text? = nil, message: Text? = nil, preview: SharePreview<PreviewImage, PreviewIcon>) where Data == CollectionOfOne<I>, I : Transferable
```

## 参数

- **title**：共享操作的标题。
- **item**：要共享的项目。
- **subject**：共享到支持主题字段的活动时要显示的项目标题。
- **message**：项目的描述，在分享到支持信息字段的活动时显示。活动可能支持归属文本或 HTML 字符串。
- **preview**：要在预览中呈现的项目表示。

## 通过预览共享项目

- **init(item:subject:message:preview:)**：创建一个显示共享界面的实例。
- **init(item:subject:message:preview:label:)**：创建显示共享接口的实例。


---
source: https://developer.apple.com/documentation/SwiftUI/ShareLink/init(_:item:subject:message:preview:)
crawled: 2025-12-01T10:34:13Z
---

# init(_:item:subject:message:preview:)

**Initializer**

Creates an instance, with a custom label, that presents the share interface.

## Declaration

```swift
nonisolated init<I>(_ title: Text, item: I, subject: Text? = nil, message: Text? = nil, preview: SharePreview<PreviewImage, PreviewIcon>) where Data == CollectionOfOne<I>, I : Transferable
```

## Parameters

- **title**: The title of the share action.
- **item**: The item to share.
- **subject**: A title for the item to show when sharing to activities that support a subject field.
- **message**: A description of the item to show when sharing to activities that support a message field. Activities may support attributed text or HTML strings.
- **preview**: A representation of the item to render in a preview.

## Sharing an item with a preview

- **init(item:subject:message:preview:)**: Creates an instance that presents the share interface.
- **init(item:subject:message:preview:label:)**: Creates an instance that presents the share interface.

