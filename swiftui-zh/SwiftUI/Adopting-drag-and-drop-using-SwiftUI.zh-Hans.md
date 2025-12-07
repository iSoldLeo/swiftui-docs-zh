--- 来源：https://developer.apple.com/documentation/SwiftUI/Adopting-drag-and-drop-using-SwiftUI
抓取时间：2025-12-02T15:50:51Z

---

# 使用 SwiftUI 实现拖放功能

**示例代码**

在列表、表格和自定义视图中启用拖放交互。

## 概述

此示例代码项目演示了如何将 SwiftUI 视图用作拖放源或拖放目标。

要启用拖放交互，请将 [draggable(_:)](View/draggable.zh-Hans.md) 修饰符添加到视图，以便在应用内、应用集合之间或应用与其他支持导入或导出指定数据格式的应用之间发送或接收 [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 项目。要处理拖放的内容，请使用 [dropDestination(for:action:isTargeted:)](View/dropDestination_for_action_isTargeted.zh-Hans.md) 修饰符来接收预期的拖放项目。

在示例应用中，用户可以将联系人从联系人列表中拖放到其他应用（例如“通讯录”、“备忘录”或“信息”）中。此外，用户还可以将其他应用（例如“通讯录”或“备忘录”）中的新联系人拖放到示例应用中。

在 iPad 上，用户可以将此示例与“通讯录”或“备忘录”等其他应用在分屏视图中使用。用户可以将此应用中的一行拖放到“通讯录”中，也可以将“通讯录”中的联系人拖放到此应用中。

### 启用拖拽交互

要启用拖拽功能，请将 `draggable(_:)` 修饰符添加到视图，以便发送符合 `Transferable` 协议的项目。

```swift
List {
    ForEach(dataModel.contacts) { contact in
        NavigationLink {
            ContactDetailView(contact: contact)
        } label: {
            CompactContactView(contact: contact)
                .draggable(contact) {
                    ThumbnailView(contact: contact)
                }
        }
    }
}
```

当用户从联系人列表中拖拽联系人时，应用会使用 [draggable(_:preview:)](View/draggable___preview.zh-Hans.md) 修饰符为拖拽的项目定义自定义预览。

要了解更多关于如何使用可拖动 API 为拖动操作提供项目的信息，请参阅 [doc://com.apple.documentation/documentation/SwiftUI/Making-a-view-into-a-drag-source]。

### 启用拖放交互

使用 `dropDestination(for:action:isTargeted:)` 修饰符接收拖动的项目，并定义处理拖放内容的目标位置。

```swift
.dropDestination(for: Contact.self) { droppedContacts, index in
    dataModel.handleDroppedContacts(droppedContacts: droppedContacts, index: index)
}
```

该修饰符需要一个符合 `Transferable` 协议的 `Contact` 类型。`dropDestination(for:action:isTargeted:)` 修饰符的实现使用 [https://developer.apple.com/coretransferable/transferrepresentation] 来接收表示拖放联系人信息的拖动项目。

应用会按优先级顺序定义传输表示。应用会使用最合适的表示来创建和初始化 `Contact` 对象。

```swift
static var transferRepresentation: some TransferRepresentation {
    // Allows a Contact to be transferred with a custom content type.
    CodableRepresentation(contentType: .exampleContact)
    // Allows importing and exporting Contact data as a vCard.
    DataRepresentation(contentType: .vCard) { contact in
        try contact.toVCardData()
    } importing: { data in
        try await parseVCardData(data)
    }
    .suggestedFileName { $0.fullName }
    // Enables exporting the `phoneNumber` string as a proxy for the entire `Contact`.
    ProxyRepresentation { contact in
        contact.phoneNumber
    } importing: { value in
        Contact(id: UUID().uuidString, givenName: value, familyName: "", phoneNumber: "")
    }
}
```

如果应用接收到一个带有自定义 [doc://com.apple.documentation/documentation/UniformTypeIdentifiers] 的项目，例如 `com.example.contact`，则它会使用 [doc://com.apple.documentation/documentation/CoreTransferable/CodableRepresentation] 来表示 `Contact` 数据结构。

示例应用声明的 `com.example.contact` 符合 public.contact 类型。为了确保操作系统能够理解如何处理内容类型，它应该符合 `UTType.data`、`UTType.package` 或继承自这两个类型的其他类型之一。

[doc://com.apple.documentation/documentation/CoreTransferable/ProxyRepresentation] 提供了一种替代表示方式，允许用户将联系人拖放到任何不支持 `com.example.contact` 或 [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct/vCard] 内容但支持文本格式的文本编辑器中。在这种情况下，应用程序会将 `phoneNumber` 导出为字符串。当用户将字符串拖放到 [List](List.zh-Hans.md) 或 [Table](Table.zh-Hans.md) 上时，示例应用程序会使用 `ProxyRepresentation` 将该字符串转换为 `Contact` 对象。

最后，[doc://com.apple.documentation/documentation/CoreTransferable/DataRepresentation] 创建 `Contact` 对象的二进制表示，并为支持 `vCard` 内容类型的接收者构建值。

当用户将联系人拖放到 `Table` 或 `List` 上时，完成处理程序会将拖放的联系人插入到拖放位置的联系人集合中。如果拖放操作未指定索引，则完成处理程序会将拖放的联系人添加到集合末尾。

```swift
func handleDroppedContacts(droppedContacts: [Contact], index: Int? = nil) {
    guard let firstContact = droppedContacts.first else {
        return
    }
    // If the ID of the first contact exists in the contacts list,
    // move the contact from its current position to the new index.
    // If no index is specified, insert the contact at the end of the list.
    if let existingIndex = contacts.firstIndex(where: { $0.id == firstContact.id }) {
        let indexSet = IndexSet(integer: existingIndex)
        contacts.move(fromOffsets: indexSet, toOffset: index ?? contacts.endIndex)
    } else {
        contacts.insert(firstContact, at: index ?? contacts.endIndex)
    }
}
```

最后，`dropDestination(for:action:isTargeted:)` 修饰符可以接收来自任何其他视图或应用的拖放交互。

有关采用拖放功能的设计指南，请参阅人机界面指南 > [https://developer.apple.com/design/human-interface-guidelines/drag-and-drop]。

## 基本要素

- **将视图转换为拖放源**：采用可拖放 API 为拖放操作提供项目。


---
source: https://developer.apple.com/documentation/SwiftUI/Adopting-drag-and-drop-using-SwiftUI
crawled: 2025-12-02T15:50:51Z
---

# Adopting drag and drop using SwiftUI

**Sample Code**

Enable drag-and-drop interactions in lists, tables and custom views.

## Overview

This sample code project demonstrates how a SwiftUI view can act as a drag source or drop destination.

To enable drag interactions, add the [draggable(_:)](View/draggable.zh-Hans.md) modifier to a view to send or receive [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] items within an app, among a collection of your own apps, or between your apps and others that support the import or export of a specified data format. To handle dropped content, use the [dropDestination(for:action:isTargeted:)](View/dropDestination_for_action_isTargeted.zh-Hans.md) modifier to receive the expected dropped item.

In the sample app, people can drag a contact from a list of contacts and drop it into another app; such as Contacts, Notes, or Messages. Additionally, people can drag and drop new contacts from other apps, like Contacts or Notes, into the sample app.

On iPad, people can use this sample with a second app such as Contacts or Notes in Split View. People can drag a row from this app into Contacts or drag a contact from Contacts into this app.

### Enable Drag Interactions

To enable dragging, add the `draggable(_:)` modifier to a view to send items that conform to `Transferable` protocol.

```swift
List {
    ForEach(dataModel.contacts) { contact in
        NavigationLink {
            ContactDetailView(contact: contact)
        } label: {
            CompactContactView(contact: contact)
                .draggable(contact) {
                    ThumbnailView(contact: contact)
                }
        }
    }
}
```

When someone drags a contact from a list of contacts, the app uses the [draggable(_:preview:)](View/draggable___preview.zh-Hans.md) modifier to define a custom preview for the dragged item.

To learn more about adopting the draggable API to provide items for drag operations, see [doc://com.apple.documentation/documentation/SwiftUI/Making-a-view-into-a-drag-source].

### Enable drop interactions

Use the `dropDestination(for:action:isTargeted:)` modifier to receive dragged items and define the destination that handles the dropped content.

```swift
.dropDestination(for: Contact.self) { droppedContacts, index in
    dataModel.handleDroppedContacts(droppedContacts: droppedContacts, index: index)
}
```

The modifier expects a type `Contact` which conforms to the `Transferable` protocol. The implementation of the `dropDestination(for:action:isTargeted:)` modifier uses the [https://developer.apple.com/coretransferable/transferrepresentation] to receive a dragged item representing the dropped contact information.

The app defines the transfer representations in order of preference. The app uses the most suitable representation to create and initialize a `Contact` object.

```swift
static var transferRepresentation: some TransferRepresentation {
    // Allows a Contact to be transferred with a custom content type.
    CodableRepresentation(contentType: .exampleContact)
    // Allows importing and exporting Contact data as a vCard.
    DataRepresentation(contentType: .vCard) { contact in
        try contact.toVCardData()
    } importing: { data in
        try await parseVCardData(data)
    }
    .suggestedFileName { $0.fullName }
    // Enables exporting the `phoneNumber` string as a proxy for the entire `Contact`.
    ProxyRepresentation { contact in
        contact.phoneNumber
    } importing: { value in
        Contact(id: UUID().uuidString, givenName: value, familyName: "", phoneNumber: "")
    }
}
```

If the app receives an item with a custom [doc://com.apple.documentation/documentation/UniformTypeIdentifiers], for example `com.example.contact`, it uses the [doc://com.apple.documentation/documentation/CoreTransferable/CodableRepresentation] to represent the `Contact` data structure.

`com.example.contact` declared by the sample app conforms to public.contact. To ensure the operating system understands how to handle the content type, it should conform to either `UTType.data`, `UTType.package`, or one of the types that inherit from these two.

[doc://com.apple.documentation/documentation/CoreTransferable/ProxyRepresentation] serves as an alternative representation that allows people to drag and drop a contact into any text editor that doesn’t support `com.example.contact` or [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct/vCard] content but works with text formats. In this case, the app exports the `phoneNumber` as a string. When someone drops a string on the [List](List.zh-Hans.md) or [Table](Table.zh-Hans.md), the sample app uses the `ProxyRepresentation` to convert that string into a `Contact` object.

Finally, [doc://com.apple.documentation/documentation/CoreTransferable/DataRepresentation] creates a binary representation of the `Contact` object and constructs the value for the receiver that supports the `vCard` content type.

When someone drops the contact on the `Table` or `List`, the completion handler inserts the dropped contact into the collection of contacts at the drop location. If the drop doesn’t specify an index, the completion handler adds the dropped contact to the end of the collection.

```swift
func handleDroppedContacts(droppedContacts: [Contact], index: Int? = nil) {
    guard let firstContact = droppedContacts.first else {
        return
    }
    // If the ID of the first contact exists in the contacts list,
    // move the contact from its current position to the new index.
    // If no index is specified, insert the contact at the end of the list.
    if let existingIndex = contacts.firstIndex(where: { $0.id == firstContact.id }) {
        let indexSet = IndexSet(integer: existingIndex)
        contacts.move(fromOffsets: indexSet, toOffset: index ?? contacts.endIndex)
    } else {
        contacts.insert(firstContact, at: index ?? contacts.endIndex)
    }
}
```

Finally, the `dropDestination(for:action:isTargeted:)` modifier can receive drag interactions that start in any other view or app.

For design guidance on adopting drag and drop, see Human Interface Guidelines > [https://developer.apple.com/design/human-interface-guidelines/drag-and-drop].

## Essentials

- **Making a view into a drag source**: Adopt draggable API to provide items for drag-and-drop operations.

