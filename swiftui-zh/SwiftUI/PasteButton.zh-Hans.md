--- 来源：https://developer.apple.com/documentation/SwiftUI/PasteButton
抓取时间：2025-12-02T17:27:36Z

---

# PasteButton

**Structure**

一个系统按钮，用于读取剪贴板中的项目并将其传递给闭包。

## 声明

```swift
@MainActor @preconcurrency struct PasteButton
```

## 概述

当您希望提供一个按钮，用于将系统剪贴板中的项目粘贴到您的应用中时，可以使用粘贴按钮。系统会根据当前环境提供合适的按钮外观和标签。但是，在某些情况下，您可以使用视图修饰符（例如 [buttonBorderShape(_:)](View/buttonBorderShape.zh-Hans.md)、[labelStyle(_:)](View/labelStyle.zh-Hans.md) 和 [tint(_:)](View/tint.zh-Hans.md)）来自定义按钮。

您需要声明您的应用将接受哪些类型的项目；使用符合 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议的类型。当用户点击或单击按钮时，您的闭包会接收指定类型的剪贴板项。

在以下示例中，粘贴按钮声明它接受字符串。当用户点击或单击按钮时，示例的闭包会接收一个字符串数组，并将第一个字符串设置为 `pastedText` 的值，从而更新附近的 [Text](Text.zh-Hans.md) 视图。

```swift
@State private var pastedText: String = ""

var body: some View {
    HStack {
        PasteButton(payloadType: String.self) { strings in
            pastedText = strings[0]
        }
        Divider()
        Text(pastedText)
        Spacer()
    }
}
```

在 iOS 上，粘贴按钮会根据剪贴板的更改自动验证和失效，但在 macOS 上则不会。

## 创建粘贴按钮

- **init(supportedContentTypes:payloadAction:)**：创建一个粘贴按钮，该按钮接受来自剪贴板的特定类型的数据。

- **init(payloadType:onPaste:)**：创建一个接受指定类型值的实例。

## 已弃用的初始化器

- **init(supportedTypes:payloadAction:)**：创建一个“粘贴”按钮，该按钮接受来自剪贴板的特定类型的数据。

- **init(supportedTypes:validator:payloadAction:)**：创建一个“粘贴”按钮，该按钮接受来自剪贴板的特定类型的数据，并在将数据发送到您的应用程序之前执行自定义验证。

- **init(supportedContentTypes:validator:payloadAction:)**：创建一个“粘贴”按钮，该按钮接受来自剪贴板的特定类型的数据，并在将数据发送到您的应用程序之前执行自定义验证。

## 创建特殊用途按钮

- **EditButton**：一个用于切换编辑模式环境值的按钮。

- **RenameButton**：一个用于触发标准重命名操作的按钮。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/SwiftUI/PasteButton
crawled: 2025-12-02T17:27:36Z
---

# PasteButton

**Structure**

A system button that reads items from the pasteboard and delivers it to a closure.

## Declaration

```swift
@MainActor @preconcurrency struct PasteButton
```

## Overview

Use a paste button when you want to provide a button for pasting items from the system pasteboard into your app. The system provides a button appearance and label appropriate to the current environment. However, you can use view modifiers like [buttonBorderShape(_:)](View/buttonBorderShape.zh-Hans.md), [labelStyle(_:)](View/labelStyle.zh-Hans.md), and [tint(_:)](View/tint.zh-Hans.md) to customize the button in some contexts.

You declare what type of items your app will accept; use a type that conforms to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol. When the user taps or clicks the button, your closure receives the pasteboard items in the specified type.

In the following example, a paste button declares that it accepts a string. When the user taps or clicks the button, the sample’s closure receives an array of strings and sets the first as the value of `pastedText`, which updates a nearby [Text](Text.zh-Hans.md) view.

```swift
@State private var pastedText: String = ""

var body: some View {
    HStack {
        PasteButton(payloadType: String.self) { strings in
            pastedText = strings[0]
        }
        Divider()
        Text(pastedText)
        Spacer()
    }
}
```



A paste button automatically validates and invalidates based on changes to the pasteboard on iOS, but not on macOS.

## Creating a paste button

- **init(supportedContentTypes:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard.
- **init(payloadType:onPaste:)**: Creates an instance that accepts values of the specified type.

## Deprecated initializers

- **init(supportedTypes:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard.
- **init(supportedTypes:validator:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard, performing a custom validation of the data before sending it to your app.
- **init(supportedContentTypes:validator:payloadAction:)**: Creates a Paste button that accepts specific types of data from the pasteboard, performing a custom validation of the data before sending it to your app.

## Creating special-purpose buttons

- **EditButton**: A button that toggles the edit mode environment value.
- **RenameButton**: A button that triggers a standard rename action.

## Conforms To

- View

