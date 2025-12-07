--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textSelection(_:)

抓取时间：2025-12-02T17:34:35Z

---

# textSelection(_:)

**实例方法**

控制用户是否可以选择此视图中的文本。

## 声明

```swift
nonisolated func textSelection<S>(_ selectability: S) -> some View where S : TextSelectability

```

## 讨论

用户有时需要从视图中复制有用的信息（例如错误消息、序列号或 IP 地址），以便将其粘贴到其他上下文中。启用文本选择功能，使用户能够以适合平台的方式选择文本。

您可以将此方法应用于单个文本视图，也可以应用于容器，使容器中的每个文本视图都可选择。在以下示例中，使用该应用的用户可以选择显示活动日期或任何活动参与者的姓名或电子邮件地址的文本：

```swift
var body: some View {
    VStack {
        Text("Event Invite")
            .font(.title)
        Text(invite.date.formatted(date: .long, time: .shortened))
            .textSelection(.enabled)

        List(invite.recipients) { recipient in
            VStack (alignment: .leading) {
                Text(recipient.name)
                Text(recipient.email)
                    .foregroundStyle(.secondary)
            }
        }
        .textSelection(.enabled)
    }
    .navigationTitle("New Invitation")
}
```

在 macOS 上，用户可以使用鼠标或触控板选择一段文本，然后通过选择“编辑”>“复制”或使用标准键盘快捷键快速复制。

在 iOS 上，使用该应用的用户触摸并按住可选择的 `Text` 视图，这将弹出一个系统菜单，其中包含与当前上下文相关的菜单项。这些菜单项操作的是 `Text` 视图中的所有内容；用户无法像在 macOS 上那样选择一段文本。

## 选择文本

- **TextSelectability**：描述选择文本功能的类型。

- **TextSelection**：表示已选择的文本。

- **textSelectionAffinity(_:)**：设置选区或光标相对于文本字符的方向。

- **textSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联关系。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 文字的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

- **TextSelectionAffinity**：表示选区或光标相对于文本字符的方向或关联关系。当处理双向文本（包含从左到右 (LTR) 和从右到左 (RTL) 文字的文本，例如英语和阿拉伯语的组合）时，此概念尤为重要。

- **AttributedTextSelection**：表示已添加属性的文本选区。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textSelection(_:)
crawled: 2025-12-02T17:34:35Z
---

# textSelection(_:)

**Instance Method**

Controls whether people can select text within this view.

## Declaration

```swift
nonisolated func textSelection<S>(_ selectability: S) -> some View where S : TextSelectability

```

## Discussion

People sometimes need to copy useful information from [Text](../Text.zh-Hans.md) views — including error messages, serial numbers, or IP addresses — so they can then paste the text into another context. Enable text selection to let people select text in a platform-appropriate way.

You can apply this method to an individual text view, or to a container to make each contained text view selectable. In the following example, the person using the app can select text that shows the date of an event or the name or email of any of the event participants:

```swift
var body: some View {
    VStack {
        Text("Event Invite")
            .font(.title)
        Text(invite.date.formatted(date: .long, time: .shortened))
            .textSelection(.enabled)

        List(invite.recipients) { recipient in
            VStack (alignment: .leading) {
                Text(recipient.name)
                Text(recipient.email)
                    .foregroundStyle(.secondary)
            }
        }
        .textSelection(.enabled)
    }
    .navigationTitle("New Invitation")
}
```

On macOS, people use the mouse or trackpad to select a range of text, which they can quickly copy by choosing Edit > Copy, or with the standard keyboard shortcut.



On iOS, the person using the app touches and holds on a selectable `Text` view, which brings up a system menu with menu items appropriate for the current context. These menu items operate on the entire contents of the `Text` view; the person can’t select a range of text like they can on macOS.





## Selecting text

- **TextSelectability**: A type that describes the ability to select text.
- **TextSelection**: Represents a selection of text.
- **textSelectionAffinity(_:)**: Sets the direction of a selection or cursor relative to a text character.
- **textSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **TextSelectionAffinity**: A representation of the direction or association of a selection or cursor relative to a text character. This concept becomes much more prominent when dealing with bidirectional text (text that contains both LTR and RTL scripts, like English and Arabic combined).
- **AttributedTextSelection**: Represents a selection of attributed text.

