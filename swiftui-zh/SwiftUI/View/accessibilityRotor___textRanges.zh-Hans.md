--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:textRanges:)

抓取时间：2025-12-02T17:44:33Z

---

# accessibilityRotor(_:textRanges:)

**实例方法**

创建一个辅助功能旋转器，并为其指定用户可见的标签以及每个指定范围的条目。该旋转器将附加到当前的辅助功能元素，每个条目将填充该元素的指定范围。

## 声明

```swift
nonisolated func accessibilityRotor(_ label: LocalizedStringResource, textRanges: [Range<String.Index>]) -> some View

```

## 参数

- **label**：用于向用户标识此旋转器的本地化标签。

- **textRanges**：用于生成旋转器条目的范围数组。

## 讨论

辅助功能旋转器 (Rotor) 是辅助功能用户快速导航到用户界面特定元素（以及可选的元素内特定文本范围）的快捷方式。

在以下示例中，消息应用程序添加了一个旋转器，允许用户浏览所有包含电子邮件地址的文本范围。

```swift
extension Message {
    // Ranges of special areas in the `content` text. Calculated
    // when `content` is set and then cached so that we don't have
    // to re-compute them.
    var emailAddressRanges: [Range<String.Index>]
}

struct MessageContentView: View {
    TextEditor(.constant(message.content))
        .accessibilityRotor("Email Addresses",
            textRanges: message.emailAddressRanges)
}
```

## 使用旋转器

- **accessibilityRotor(_:entries:)**：创建一个具有指定用户可见标签的辅助功能旋转器，并使用从内容闭包生成的条目。

- **accessibilityRotor(_:entries:entryID:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能旋转器。

- **accessibilityRotor(_:entries:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能旋转器。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:textRanges:)
crawled: 2025-12-02T17:44:33Z
---

# accessibilityRotor(_:textRanges:)

**Instance Method**

Create an Accessibility Rotor with the specified user-visible label and entries for each of the specified ranges. The Rotor will be attached to the current Accessibility element, and each entry will go the specified range of that element.

## Declaration

```swift
nonisolated func accessibilityRotor(_ label: LocalizedStringResource, textRanges: [Range<String.Index>]) -> some View

```

## Parameters

- **label**: Localized label identifying this Rotor to the user.
- **textRanges**: An array of ranges that will be used to generate the entries of the Rotor.

## Discussion

An Accessibility Rotor is a shortcut for Accessibility users to quickly navigate to specific elements of the user interface, and optionally specific ranges of text within those elements.

In the following example, a Message application adds a Rotor allowing the user to navigate through all the ranges of text containing email addresses.

```swift
extension Message {
    // Ranges of special areas in the `content` text. Calculated
    // when `content` is set and then cached so that we don't have
    // to re-compute them.
    var emailAddressRanges: [Range<String.Index>]
}

struct MessageContentView: View {
    TextEditor(.constant(message.content))
        .accessibilityRotor("Email Addresses",
            textRanges: message.emailAddressRanges)
}
```

## Working with rotors

- **accessibilityRotor(_:entries:)**: Create an Accessibility Rotor with the specified user-visible label, and entries generated from the content closure.
- **accessibilityRotor(_:entries:entryID:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:entries:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.

