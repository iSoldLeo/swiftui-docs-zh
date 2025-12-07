---
来源： https://developer.apple.com/documentation/SwiftUI/Making-a-view-into-a-drag-source
抓取时间： 2025-12-02T16:15:45Z
---

# 将视图变为拖动源

**Article**

采用可拖动 API，为拖放操作提供项目。

### 概览

当有人在您的应用程序中拖动屏幕上项目的可视化表示（如照片、地图位置、日历事件或文本选择）时，拖动操作会关联一些数据以及系统显示的数据预览。添加[draggable(_:)](View/draggable.zh-Hans.md)修饰符以启用视图作为拖动源，并提供符合[doc://com.apple.documentation/documentation/CoreTransferable/Transferable] 协议的值。

`Transferable`协议描述了如何将模型对象序列化和反序列化，以便进行共享和数据传输。它通过组合一个或多个核心可传输框架的内置[doc://com.apple.documentation/documentation/CoreTransferable/TransferRepresentation] 类型来提供传输表示。

### 启用视图作为拖动源

使用`draggable(_:)`修饰符可在应用程序内部、您自己的应用程序集合之间，或在您的应用程序与其他支持导入或导出指定数据格式的应用程序之间发送或接收`Transferable`项目。

```swift
struct MyView: View {
    let name = "Mei Chen"
    
    var body: some View {
        Text(name)
            .draggable(name)
    }
}
```

使用[draggable(_:preview:)](View/draggable___preview.zh-Hans.md)修饰符为拖动的项目定义自定义预览。

```swift
    Text(name)
        .draggable(name) {
            ZStack {
                RoundedRectangle(cornerRadius: 10)
                    .frame(width: 300, height: 300)
                    .foregroundStyle(.yellow.gradient)
                Text("Drop \(name)")
                    .font(.title)
                    .foregroundStyle(.red)
            }
        }
```

要自定义系统在过渡到显示自定义`preview` 时显示的提升预览，请应用带有[dragPreview](ContentShapeKinds/dragPreview.zh-Hans.md) 类型的[contentShape(_:_:eoFill:)](View/contentShape_____eoFill.zh-Hans.md) 修改器。例如，您可以更改预览的边角半径，如下代码示例所示：

```swift
    Text(name)
        .contentShape(.dragPreview, RoundedRectangle(cornerRadius: 7))
        .draggable(name) {
            ZStack {
                RoundedRectangle(cornerRadius: 20)
                    .frame(width: 300, height: 300)
                    .foregroundStyle(.yellow.gradient)
                Text("Drop \(name)")
                    .font(.title)
                    .foregroundStyle(.red)
            }
        }
```

### 为拖放操作创建可转移的项目

要支持模型对象的拖放操作，请使模型符合`Transferable` 协议以创建可转移项，并实现[doc://com.apple.documentation/documentation/CoreTransferable/TransferRepresentation] 静态属性。[doc://com.apple.documentation/documentation/Swift/String]、[doc://com.apple.documentation/documentation/Foundation/Data]、[doc://com.apple.documentation/documentation/Foundation/URL] 和[doc://com.apple.documentation/documentation/SwiftUI/Image] 等类型已经符合`Transferable` 协议，因此在拖放操作中很容易使用。

定义一个代表用户配置文件的数据模型，该数据模型是符合[doc://com.apple.documentation/documentation/Swift/Codable] 的类型，具有`name` 和`phoneNumber` 属性。

```swift
struct Profile: Codable, Identifiable {
    var id: UUID = UUID()
    var name: String
    var phoneNumber: String
}
```

扩展`Profile`，使其符合`Transferable`协议，以组成传输表示法，并添加带有自定义统一类型标识符`com.example.profile`的[doc://com.apple.documentation/documentation/CoreTransferable/CodableRepresentation]，以表示⟦数据结构。

```swift
extension Profile: Transferable {
    static var transferRepresentation: some TransferRepresentation {
        CodableRepresentation(contentType: .profile)
        ProxyRepresentation(exporting: \.name)
    }
}
```

确保在应用程序的 `Info.plist` 文件中包含自定义统一类型标识符。有关详细信息，请参阅 [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/defining-file-and-data-types-for-your-app]。

在 [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct] 上将新的统一类型标识符声明为方便变量。对于导出声明，请使用下面的代码：

```swift
extension UTType {
    static var profile = UTType(exportedAs: "com.example.profile")
}
```

上一代码示例中的另一种传输表示类型是[doc://com.apple.documentation/documentation/CoreTransferable/ProxyRepresentation]，它使用`String`结构的内置`Transferable`一致性。`ProxyRepresentation`作为一种替代方法，可让人们在任何不支持`com.example.profile`内容类型但可处理文本格式的文本编辑器中拖放配置文件项。

要为可拖动项目添加更多传输表示法，请按首选顺序指定一个或多个附加表示法。这可确保系统根据接收方可接受拖放操作的内容类型，使用最合适的表示法。有关更多信息，请参阅 [doc://com.apple.documentation/documentation/CoreTransferable/choosing-a-transfer-representation-for-a-model-type]。

要将`com.example.profile` 内容类型用于拖放操作，请将`draggable(_:)` 配置文件传递给`draggable(_:)` 修改器。

```swift
struct ContentView: View {
    @State private var profiles = [
        Profile(name: "Juan Chavez", phoneNumber: "(408) 555-4301"),
        Profile(name: "Mei Chen", phoneNumber: "(919) 555-2481")
    ]
    
    var body: some View {
        List {
            ForEach(profiles) { profile in
                Text(profile.name)
                    .draggable(profile)
            }
        }
    }
}
```

### 启用列表重排序

在[List](List.zh-Hans.md) 中，可以使用[onMove(perform:)](DynamicViewContent/onMove_perform.zh-Hans.md) 修饰符来启用重新排序。使用该修饰符，可以长按一行，然后将其拖动到新位置，从而对列表项重新排序。将`onMove(perform:)`修饰符添加到`List` 以启用交互。

```swift
    List {
        ForEach(profiles) { profile in
            Text(profile.name)
        }
        .onMove { indices, newOffset in
            // Update the items array based on source and destination indices.
            profiles.move(fromOffsets: indices, toOffset: newOffset)
        }
    }
```

要有条件地禁用特定行上的项目重排序，请将[moveDisabled(_:)](View/moveDisabled.zh-Hans.md) 设置为`true`。

### 要点

- 使用 SwiftUI**进行拖放**：在列表、表格和自定义视图中启用拖放交互。


---
source: https://developer.apple.com/documentation/SwiftUI/Making-a-view-into-a-drag-source
crawled: 2025-12-02T16:15:45Z
---

# Making a view into a drag source

**Article**

Adopt draggable API to provide items for drag-and-drop operations.

## Overview

When someone drags an onscreen visual representation of an item in your app, such as a photo, a Maps location, a Calendar event, or a text selection, the drag operation has some data associated with it, as well as a preview of the data that the system displays. Add the [draggable(_:)](View/draggable.zh-Hans.md) modifier to enable the view to function as a drag source, and provide a value that conforms to the [doc://com.apple.documentation/documentation/CoreTransferable/Transferable] protocol.

The `Transferable` protocol describes how you can serialize and deserialize your model object for sharing and data transfer. It provides a transfer representation by composing one or more of the Core Transferable framework’s built-in [doc://com.apple.documentation/documentation/CoreTransferable/TransferRepresentation] types.

### Enable a view as a drag source

Use the `draggable(_:)` modifier to send or receive `Transferable` items within an app, among a collection of your own apps, or between your apps and other apps that support the import or export of a specified data format.

```swift
struct MyView: View {
    let name = "Mei Chen"
    
    var body: some View {
        Text(name)
            .draggable(name)
    }
}
```

Use the [draggable(_:preview:)](View/draggable___preview.zh-Hans.md) modifier to define a custom preview for the dragged item.

```swift
    Text(name)
        .draggable(name) {
            ZStack {
                RoundedRectangle(cornerRadius: 10)
                    .frame(width: 300, height: 300)
                    .foregroundStyle(.yellow.gradient)
                Text("Drop \(name)")
                    .font(.title)
                    .foregroundStyle(.red)
            }
        }
```

To customize the lift preview that the system shows as it transitions to displaying your custom `preview`, apply a [contentShape(_:_:eoFill:)](View/contentShape_____eoFill.zh-Hans.md) modifier with a [dragPreview](ContentShapeKinds/dragPreview.zh-Hans.md) kind. For example, you can change the preview’s corner radius, as in the following code example:

```swift
    Text(name)
        .contentShape(.dragPreview, RoundedRectangle(cornerRadius: 7))
        .draggable(name) {
            ZStack {
                RoundedRectangle(cornerRadius: 20)
                    .frame(width: 300, height: 300)
                    .foregroundStyle(.yellow.gradient)
                Text("Drop \(name)")
                    .font(.title)
                    .foregroundStyle(.red)
            }
        }
```

### Create a transferable item for drag-and-drop operations

To support drag operations of model objects, conform a model to the `Transferable` protocol to create a transferable item, and implement the [doc://com.apple.documentation/documentation/CoreTransferable/TransferRepresentation] static property. Types like [doc://com.apple.documentation/documentation/Swift/String], [doc://com.apple.documentation/documentation/Foundation/Data], [doc://com.apple.documentation/documentation/Foundation/URL], and [doc://com.apple.documentation/documentation/SwiftUI/Image] already conform to `Transferable`, making them easy to use in drag-and-drop operations.

Define a data model, representing a user profile, that is a type conforming to [doc://com.apple.documentation/documentation/Swift/Codable] with the properties `name` and `phoneNumber`.

```swift
struct Profile: Codable, Identifiable {
    var id: UUID = UUID()
    var name: String
    var phoneNumber: String
}
```

Extend `Profile` to conform to the `Transferable` protocol to compose a transfer representation, and add [doc://com.apple.documentation/documentation/CoreTransferable/CodableRepresentation] with the custom uniform type identifier `com.example.profile` to represent the `Profile` data structure.

```swift
extension Profile: Transferable {
    static var transferRepresentation: some TransferRepresentation {
        CodableRepresentation(contentType: .profile)
        ProxyRepresentation(exporting: \.name)
    }
}
```

Make sure to include the custom uniform type identifier in the app’s `Info.plist` file. For more information, see [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/defining-file-and-data-types-for-your-app].

Declare new uniform type identifiers as convenience variables on [doc://com.apple.documentation/documentation/UniformTypeIdentifiers/UTType-swift.struct]. For an exported declaration, use the following code:

```swift
extension UTType {
    static var profile = UTType(exportedAs: "com.example.profile")
}
```

The other type of transfer representation in the previous code example is a [doc://com.apple.documentation/documentation/CoreTransferable/ProxyRepresentation], which uses the `String` structure’s built-in `Transferable` conformance. `ProxyRepresentation` serves as an alternative that lets people drag and drop the profile item in any text editor that doesn’t support the `com.example.profile` content type, but works with text formats.

To add more transfer representations to a draggable item, specify one or more additional representations in order of preference. This ensures that the system uses the most suitable representation, depending on the content type that the receiver can accept for drag-and-drop operations. For more information, see [doc://com.apple.documentation/documentation/CoreTransferable/choosing-a-transfer-representation-for-a-model-type].

To use the `com.example.profile` content type for drag operations, pass in the profiles to the `draggable(_:)` modifier.

```swift
struct ContentView: View {
    @State private var profiles = [
        Profile(name: "Juan Chavez", phoneNumber: "(408) 555-4301"),
        Profile(name: "Mei Chen", phoneNumber: "(919) 555-2481")
    ]
    
    var body: some View {
        List {
            ForEach(profiles) { profile in
                Text(profile.name)
                    .draggable(profile)
            }
        }
    }
}
```

### Enable list reordering

Within a [List](List.zh-Hans.md), you can use the [onMove(perform:)](DynamicViewContent/onMove_perform.zh-Hans.md) modifier to enable reordering. The modifier allows you to reorder list items by using a long press on a row, and then dragging it to a new location. Add the `onMove(perform:)` modifier to a `List` to enable the interaction.

```swift
    List {
        ForEach(profiles) { profile in
            Text(profile.name)
        }
        .onMove { indices, newOffset in
            // Update the items array based on source and destination indices.
            profiles.move(fromOffsets: indices, toOffset: newOffset)
        }
    }
```

To conditionally disable item reordering on a specific row, set [moveDisabled(_:)](View/moveDisabled.zh-Hans.md) to `true`.

## Essentials

- **Adopting drag and drop using SwiftUI**: Enable drag-and-drop interactions in lists, tables and custom views.

