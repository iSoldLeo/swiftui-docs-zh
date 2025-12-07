--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:entries:entryLabel:)

抓取时间：2025-12-02T17:44:33Z

---

# accessibilityRotor(_:entries:entryLabel:)

**实例方法**

创建一个具有指定用户可见标签和条目的辅助功能旋转器。

## 声明

```swift
nonisolated func accessibilityRotor<EntryModel>(_ rotorLabel: Text, entries: [EntryModel], entryLabel: KeyPath<EntryModel, String>) -> some View where EntryModel : Identifiable

```

## 参数

- **rotorLabel**：用于向用户标识此旋转器的本地化标签。

- **entries**：用于生成旋转器条目的可识别值数组。 `Identifiable` 值的标识符必须与 `ForEach` 中的标识符或 `id` 中显式调用的标识符匹配。当用户从此 Rotor 导航到条目时，SwiftUI 会根据需要自动将其滚动到位。

- **entryLabel**：`Identifiable` 类型的键路径，可用于获取每个 Rotor 条目的用户可见标签。在 macOS 上，当用户打开 Rotor 的条目列表时会使用此路径。

## 讨论

辅助功能 Rotor 是辅助功能用户快速导航到用户界面特定元素（以及可选的这些元素内的特定文本范围）的快捷方式。

使用此修饰符要求 Rotor 必须附加到 `ScrollView`，或直接附加到 `ScrollView` 内的辅助功能元素，例如 `ForEach`。

在以下示例中，消息应用程序创建了一个 Rotor，允许用户导航到特定来自 VIP 的消息。

```swift
// `messages` is a list of `Identifiable` `Message`s that have a
// `subject`.
// `vipMessages` is a filtered version of that list containing only
// messages from VIPs.

ScrollView {
    LazyVStack {
        ForEach(messages) { message in
            MessageView(message)
        }
    }
}
.accessibilityElement(children: .contain)
.accessibilityRotor("VIPs", entries: vipMessages, label: \.subject)
```

## 使用 Rotor

- **accessibilityRotor(_:entries:)**：创建一个具有指定用户可见标签的辅助功能 Rotor，以及从内容闭包生成的条目。

- **accessibilityRotor(_:entries:entryID:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能 Rotor。

- **accessibilityRotor(_:textRanges:)**：创建一个具有指定用户可见标签和每个指定范围条目的辅助功能 Rotor。旋转器将附加到当前的辅助功能元素上，并且每个条目都将在该元素的指定范围内运行。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:entries:entryLabel:)
crawled: 2025-12-02T17:44:33Z
---

# accessibilityRotor(_:entries:entryLabel:)

**Instance Method**

Create an Accessibility Rotor with the specified user-visible label and entries.

## Declaration

```swift
nonisolated func accessibilityRotor<EntryModel>(_ rotorLabel: Text, entries: [EntryModel], entryLabel: KeyPath<EntryModel, String>) -> some View where EntryModel : Identifiable

```

## Parameters

- **rotorLabel**: Localized label identifying this Rotor to the user.
- **entries**: An array of identifiable values that will be used to generate the entries of the Rotor. The identifiers of the `Identifiable` values must match up with identifiers in a `ForEach` or explicit `id` calls within the `ScrollView`. When the user navigates to entries from this Rotor, SwiftUI will automatically scroll them into place as needed.
- **entryLabel**: Key path on the `Identifiable` type that can be used to get a user-visible label for every Rotor entry. This is used on macOS when the user opens the list of entries for the Rotor.

## Discussion

An Accessibility Rotor is a shortcut for Accessibility users to quickly navigate to specific elements of the user interface, and optionally specific ranges of text within those elements.

Using this modifier requires that the Rotor be attached to a `ScrollView`, or an Accessibility Element directly within a `ScrollView`, such as a `ForEach`.

In the following example, a Message application creates a Rotor allowing users to navigate to specifically the messages originating from VIPs.

```swift
// `messages` is a list of `Identifiable` `Message`s that have a
// `subject`.
// `vipMessages` is a filtered version of that list containing only
// messages from VIPs.

ScrollView {
    LazyVStack {
        ForEach(messages) { message in
            MessageView(message)
        }
    }
}
.accessibilityElement(children: .contain)
.accessibilityRotor("VIPs", entries: vipMessages, label: \.subject)
```

## Working with rotors

- **accessibilityRotor(_:entries:)**: Create an Accessibility Rotor with the specified user-visible label, and entries generated from the content closure.
- **accessibilityRotor(_:entries:entryID:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:textRanges:)**: Create an Accessibility Rotor with the specified user-visible label and entries for each of the specified ranges. The Rotor will be attached to the current Accessibility element, and each entry will go the specified range of that element.

