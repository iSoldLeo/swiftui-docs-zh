---
来源： https://developer.apple.com/documentation/SwiftUI/Form
抓取时间： 2025-12-02T17:27:04Z
---

# 表格

**Structure**

用于分组数据输入控件的容器，如设置或检查器中的控件。

## 声明

```swift
struct Form<Content> where Content : View
```

## 概览

SwiftUI 会对表单中的视图应用与平台相适应的样式，以便将它们组合在一起。特定于表单的样式适用于按钮、切换按钮、标签、列表等。请记住，这些样式可能是特定于平台的。例如，iOS 上的表单显示为分组列表，而 macOS 上的表单显示为对齐的垂直堆栈。

下面的示例显示了 iOS 上的一个简单数据输入表单，分为两个部分。为简单起见，省略了支持类型（↪Ps_0009⟧ 和 ⟦⟧）和状态变量（↪Ps_0007⟧、⟦⟧、⟦⟧、↪Ps_0005⟧ 和 ⟦⟧）。

```swift
var body: some View {
    NavigationView {
        Form {
            Section(header: Text("Notifications")) {
                Picker("Notify Me About", selection: $notifyMeAbout) {
                    Text("Direct Messages").tag(NotifyMeAboutType.directMessages)
                    Text("Mentions").tag(NotifyMeAboutType.mentions)
                    Text("Anything").tag(NotifyMeAboutType.anything)
                }
                Toggle("Play notification sounds", isOn: $playNotificationSounds)
                Toggle("Send read receipts", isOn: $sendReadReceipts)
            }
            Section(header: Text("User Profiles")) {
                Picker("Profile Image Size", selection: $profileImageSize) {
                    Text("Large").tag(ProfileImageSize.large)
                    Text("Medium").tag(ProfileImageSize.medium)
                    Text("Small").tag(ProfileImageSize.small)
                }
                Button("Clear Image Cache") {}
            }
        }
    }
}
```



在 macOS 上，类似的表单渲染为垂直堆栈。为了遵守 macOS 平台的惯例，该版本不使用分段，而是在标签末尾使用冒号。此外，它还将选择器设置为使用[inline](PickerStyle/inline.zh-Hans.md) 样式，这种样式在 macOS 上可生成单选按钮。

```swift
var body: some View {
    Spacer()
    HStack {
        Spacer()
        Form {
            Picker("Notify Me About:", selection: $notifyMeAbout) {
                Text("Direct Messages").tag(NotifyMeAboutType.directMessages)
                Text("Mentions").tag(NotifyMeAboutType.mentions)
                Text("Anything").tag(NotifyMeAboutType.anything)
            }
            Toggle("Play notification sounds", isOn: $playNotificationSounds)
            Toggle("Send read receipts", isOn: $sendReadReceipts)

            Picker("Profile Image Size:", selection: $profileImageSize) {
                Text("Large").tag(ProfileImageSize.large)
                Text("Medium").tag(ProfileImageSize.medium)
                Text("Small").tag(ProfileImageSize.small)
            }
            .pickerStyle(.inline)

            Button("Clear Image Cache") {}
        }
        Spacer()
    }
    Spacer()
}
```



## 创建表格

- **init(content:)**：用提供的内容创建表格。

## 从配置创建表格

- **init(_:)**：根据表单样式配置创建表单。

## 分组输入

- **formStyle(_:)**：为视图层次结构中的表单设置样式。
- **LabeledContent**：用于将标签附加到带值视图的容器。
- **labeledContentStyle(_:)**：为标签内容设置样式。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/Form
crawled: 2025-12-02T17:27:04Z
---

# Form

**Structure**

A container for grouping controls used for data entry, such as in settings or inspectors.

## Declaration

```swift
struct Form<Content> where Content : View
```

## Overview

SwiftUI applies platform-appropriate styling to views contained inside a form, to group them together. Form-specific styling applies to things like buttons, toggles, labels, lists, and more. Keep in mind that these stylings may be platform-specific. For example, forms appear as grouped lists on iOS, and as aligned vertical stacks on macOS.

The following example shows a simple data entry form on iOS, grouped into two sections. The supporting types (`NotifyMeAboutType` and `ProfileImageSize`) and state variables (`notifyMeAbout`, `profileImageSize`, `playNotificationSounds`, and `sendReadReceipts`) are omitted for simplicity.

```swift
var body: some View {
    NavigationView {
        Form {
            Section(header: Text("Notifications")) {
                Picker("Notify Me About", selection: $notifyMeAbout) {
                    Text("Direct Messages").tag(NotifyMeAboutType.directMessages)
                    Text("Mentions").tag(NotifyMeAboutType.mentions)
                    Text("Anything").tag(NotifyMeAboutType.anything)
                }
                Toggle("Play notification sounds", isOn: $playNotificationSounds)
                Toggle("Send read receipts", isOn: $sendReadReceipts)
            }
            Section(header: Text("User Profiles")) {
                Picker("Profile Image Size", selection: $profileImageSize) {
                    Text("Large").tag(ProfileImageSize.large)
                    Text("Medium").tag(ProfileImageSize.medium)
                    Text("Small").tag(ProfileImageSize.small)
                }
                Button("Clear Image Cache") {}
            }
        }
    }
}
```



On macOS, a similar form renders as a vertical stack. To adhere to macOS platform conventions, this version doesn’t use sections, and uses colons at the end of its labels. It also sets the picker to use the [inline](PickerStyle/inline.zh-Hans.md) style, which produces radio buttons on macOS.

```swift
var body: some View {
    Spacer()
    HStack {
        Spacer()
        Form {
            Picker("Notify Me About:", selection: $notifyMeAbout) {
                Text("Direct Messages").tag(NotifyMeAboutType.directMessages)
                Text("Mentions").tag(NotifyMeAboutType.mentions)
                Text("Anything").tag(NotifyMeAboutType.anything)
            }
            Toggle("Play notification sounds", isOn: $playNotificationSounds)
            Toggle("Send read receipts", isOn: $sendReadReceipts)

            Picker("Profile Image Size:", selection: $profileImageSize) {
                Text("Large").tag(ProfileImageSize.large)
                Text("Medium").tag(ProfileImageSize.medium)
                Text("Small").tag(ProfileImageSize.small)
            }
            .pickerStyle(.inline)

            Button("Clear Image Cache") {}
        }
        Spacer()
    }
    Spacer()
}
```



## Creating a form

- **init(content:)**: Creates a form with the provided content.

## Creating a form from a configuration

- **init(_:)**: Creates a form based on a form style configuration.

## Grouping inputs

- **formStyle(_:)**: Sets the style for forms in a view hierarchy.
- **LabeledContent**: A container for attaching a label to a value-bearing view.
- **labeledContentStyle(_:)**: Sets a style for labeled content.

## Conforms To

- View

