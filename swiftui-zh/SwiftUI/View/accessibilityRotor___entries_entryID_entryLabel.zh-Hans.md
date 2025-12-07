--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:entries:entryID:entryLabel:)

抓取时间：2025-11-30T21:29:30Z

---

# accessibilityRotor(_:entries:entryID:entryLabel:)

**实例方法**

创建一个具有指定用户可见标签和条目的辅助功能旋转器。

## 声明

```swift
nonisolated func accessibilityRotor<EntryModel, ID>(_ rotorLabel: Text, entries: [EntryModel], entryID: KeyPath<EntryModel, ID>, entryLabel: KeyPath<EntryModel, String>) -> some View where ID : Hashable

```

## 参数

- **rotorLabel**：用于向用户标识此旋转器的本地化标签。

- **entries**：用于生成旋转器条目的值数组。

- **entryID**：条目类型上的键路径，可用于生成条目的标识符。标识符必须与 `ForEach` 中的标识符或 `id` 中显式调用的标识符匹配。

- **entryLabel**：条目类型上的快捷键路径，可用于获取每个 Rotor 条目的用户可见标签。在 macOS 上，当用户打开 Rotor 的条目列表时会使用此快捷键。

## 讨论

辅助功能 Rotor 是辅助功能用户快速导航到用户界面特定元素（以及可选的这些元素内的特定文本范围）的快捷方式。

使用此修饰符要求 Rotor 附加到 `ScrollView`，或附加到 `ScrollView` 内的辅助功能元素（例如 `ForEach`）。当用户通过此 Rotor 导航到条目时，SwiftUI 会根据需要自动将其滚动到位。

在以下示例中，消息应用程序创建了一个 Rotor，允许用户导航到来自 VIP 的消息。

```swift
// `messages` is a list of `Message`s that have a `subject` and a
// `uuid`. `vipMessages` is a filtered version of that list
// containing only messages from VIPs.
ScrollView {
    LazyVStack {
        ForEach(messages) { message in
            MessageView(message)
        }
    }
}
.accessibilityElement(children: .contain)
.accessibilityRotor("VIPs", entries: vipMessages,
    id: \.uuid, label: \.subject)
```

## 使用 Rotor

- **accessibilityRotor(_:entries:)**：创建一个具有指定用户可见标签的辅助功能 Rotor，条目由内容闭包生成。

- **accessibilityRotor(_:entries:entryLabel:)**：创建一个具有指定用户可见标签和条目的辅助功能 Rotor。

- **accessibilityRotor(_:textRanges:)**：创建一个具有指定用户可见标签和每个指定范围条目的辅助功能 Rotor。该 Rotor 将附加到当前的辅助功能元素，每个条目将位于该元素的指定范围内。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityRotor(_:entries:entryID:entryLabel:)
crawled: 2025-11-30T21:29:30Z
---

# accessibilityRotor(_:entries:entryID:entryLabel:)

**Instance Method**

Create an Accessibility Rotor with the specified user-visible label and entries.

## Declaration

```swift
nonisolated func accessibilityRotor<EntryModel, ID>(_ rotorLabel: Text, entries: [EntryModel], entryID: KeyPath<EntryModel, ID>, entryLabel: KeyPath<EntryModel, String>) -> some View where ID : Hashable

```

## Parameters

- **rotorLabel**: Localized label identifying this Rotor to the user.
- **entries**: An array of values that will be used to generate the entries of the Rotor.
- **entryID**: Key path on the entry type that can be used to generate an identifier for the Entry. The identifiers must match up with identifiers in `ForEach` or explicit `id` calls within the `ScrollView`.
- **entryLabel**: Key path on the entry type that can be used to get a user-visible label for every Rotor entry. This is used on macOS when the user opens the list of entries for the Rotor.

## Discussion

An Accessibility Rotor is a shortcut for Accessibility users to quickly navigate to specific elements of the user interface, and optionally specific ranges of text within those elements.

Using this modifier requires that the Rotor be attached to a `ScrollView`, or an Accessibility Element directly within a `ScrollView`, such as a `ForEach`. When the user navigates to entries from this Rotor, SwiftUI will automatically scroll them into place as needed.

In the following example, a Message application creates a Rotor allowing users to navigate to specifically the messages originating from VIPs.

```swift
// `messages` is a list of `Message`s that have a `subject` and a
// `uuid`. `vipMessages` is a filtered version of that list
// containing only messages from VIPs.
ScrollView {
    LazyVStack {
        ForEach(messages) { message in
            MessageView(message)
        }
    }
}
.accessibilityElement(children: .contain)
.accessibilityRotor("VIPs", entries: vipMessages,
    id: \.uuid, label: \.subject)
```

## Working with rotors

- **accessibilityRotor(_:entries:)**: Create an Accessibility Rotor with the specified user-visible label, and entries generated from the content closure.
- **accessibilityRotor(_:entries:entryLabel:)**: Create an Accessibility Rotor with the specified user-visible label and entries.
- **accessibilityRotor(_:textRanges:)**: Create an Accessibility Rotor with the specified user-visible label and entries for each of the specified ranges. The Rotor will be attached to the current Accessibility element, and each entry will go the specified range of that element.

