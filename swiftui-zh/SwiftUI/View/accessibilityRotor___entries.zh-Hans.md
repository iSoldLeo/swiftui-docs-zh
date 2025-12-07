--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:entries:)

抓取时间：2025-12-02T17:44:31Z

---

# accessibilityRotor(_:entries:)

**实例方法**

创建一个带有指定用户可见标签的辅助功能旋转器，以及由内容闭包生成的条目。

## 声明

```swift
nonisolated func accessibilityRotor<Content>(_ label: LocalizedStringResource, @AccessibilityRotorContentBuilder entries: @escaping () -> Content) -> some View where Content : AccessibilityRotorContent

```

## 参数

- **label**：用于向用户标识此旋转器的本地化标签。

- **entries**：用于生成旋转器条目的内容。这可以包括 AccessibilityRotorEntry 结构体，以及诸如 if 和 ForEach 之类的构造。

## 讨论

辅助功能旋转器 (Rotor) 是辅助功能用户快速导航到用户界面特定元素（以及可选的元素内特定文本范围）的快捷方式。

在以下示例中，消息应用程序创建了一个旋转器，允许用户导航到来自 VIP 的消息。

```swift
// `messages` is a list of `Identifiable` `Message`s.

ScrollView {
    LazyVStack {
        ForEach(messages) { message in
            MessageView(message)
        }
    }
}
.accessibilityElement(children: .contain)
.accessibilityRotor("VIPs") {
    // Not all the MessageViews are generated at once, the model
    // knows about all the messages.
    ForEach(messages) { message in
        // If the Message is from a VIP, make a Rotor entry for it.
        if message.isVIP {
            AccessibilityRotorEntry(message.subject, id: message.id)
        }
    }
}
```

## 使用旋转器

- **accessibilityRotor(_:entries:entryID:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能旋转器。

- **accessibilityRotor(_:entries:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能旋转器。

- **accessibilityRotor(_:textRanges:)**：创建一个具有指定用户可见标签和每个指定范围条目的辅助功能旋转器。旋转器将附加到当前的辅助功能元素，每个条目将指向该元素的指定范围。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:entries:)
crawled: 2025-12-02T17:44:31Z
---

# accessibilityRotor(_:entries:)

**Instance Method**

Create an Accessibility Rotor with the specified user-visible label, and entries generated from the content closure.

## Declaration

```swift
nonisolated func accessibilityRotor<Content>(_ label: LocalizedStringResource, @AccessibilityRotorContentBuilder entries: @escaping () -> Content) -> some View where Content : AccessibilityRotorContent

```

## Parameters

- **label**: Localized label identifying this Rotor to the user.
- **entries**: Content used to generate Rotor entries. This can include AccessibilityRotorEntry structs, as well as constructs such as if and ForEach.

## Discussion

An Accessibility Rotor is a shortcut for Accessibility users to quickly navigate to specific elements of the user interface, and optionally specific ranges of text within those elements.

In the following example, a Message application creates a Rotor allowing users to navigate to specifically the messages originating from VIPs.

```swift
// `messages` is a list of `Identifiable` `Message`s.

ScrollView {
    LazyVStack {
        ForEach(messages) { message in
            MessageView(message)
        }
    }
}
.accessibilityElement(children: .contain)
.accessibilityRotor("VIPs") {
    // Not all the MessageViews are generated at once, the model
    // knows about all the messages.
    ForEach(messages) { message in
        // If the Message is from a VIP, make a Rotor entry for it.
        if message.isVIP {
            AccessibilityRotorEntry(message.subject, id: message.id)
        }
    }
}
```

## Working with rotors

- **accessibilityRotor(_:entries:entryID:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:entries:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:textRanges:)**: Create an Accessibility Rotor with the specified user-visible label and entries for each of the specified ranges. The Rotor will be attached to the current Accessibility element, and each entry will go the specified range of that element.

