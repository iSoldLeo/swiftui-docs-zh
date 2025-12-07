---
来源： https://developer.apple.com/documentation/SwiftUI/TextSelectability/enabled
抓取时间： 2025-12-03T06:17:29Z
---

# 已启用

**类型属性**

一个选择性值，可让使用应用程序的人选择文本。

## 声明

```swift
static var enabled: EnabledTextSelectability { get }
```

## 讨论

启用文本选择可让用户对文本内容执行复制和共享等操作。在有用的视图中启用文本选择，如复制唯一 ID 或错误信息。这样，用户就可以将数据粘贴到电子邮件或文档中。

下面的示例在一个 [Text](../Text.zh-Hans.md) 视图中的两个 [VStack](../VStack.zh-Hans.md) 视图的第二个视图中启用了文本选择功能。

```swift
VStack {
    Text("Event Invite")
        .font(.title)
    Text(invite.date.formatted(date: .long, time: .shortened))
        .textSelection(.enabled)
}
```

## 获取可选择性选项

- **disabled**：选择性值，用于禁止使用您应用程序的用户选择文本。


---
source: https://developer.apple.com/documentation/SwiftUI/TextSelectability/enabled
crawled: 2025-12-03T06:17:29Z
---

# enabled

**Type Property**

A selectability value that enables text selection by a person using your app.

## Declaration

```swift
static var enabled: EnabledTextSelectability { get }
```

## Discussion

Enabling text selection allows people to perform actions on the text content, such as copying and sharing. Enable text selection in views where those operations are useful, such as copying unique IDs or error messages. This allows people to paste the data into emails or documents.

The following example enables text selection on the second of two [Text](../Text.zh-Hans.md) views in a [VStack](../VStack.zh-Hans.md).

```swift
VStack {
    Text("Event Invite")
        .font(.title)
    Text(invite.date.formatted(date: .long, time: .shortened))
        .textSelection(.enabled)
}
```

## Getting selectability options

- **disabled**: A selectability value that disables text selection by the person using your app.

