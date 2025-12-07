--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationPath
抓取时间：2025-12-02T17:29:30Z

---

# NavigationPath

**Structure**

一个类型擦除的数据列表，表示导航栈的内容。

## 声明

```swift
struct NavigationPath
```

## 概述

您可以通过将栈绑定到数据集合来管理 [NavigationStack](NavigationStack.zh-Hans.md) 的状态。栈会将集合中的数据项存储在栈上每个视图的数据中。您还可以读取和写入该集合来观察和修改栈的状态。

当栈显示的视图仅依赖于一种数据类型时，您可以使用标准集合（例如数组）来保存数据。如果需要在单个栈中呈现不同类型的数据，请改用导航路径。路径使用类型擦除，因此您可以管理异构元素的集合。路径还提供常用的集合控件，用于添加、计数和删除数据元素。

### 序列化路径

当您在导航栈上呈现的值符合 [doc://com.apple.documentation/documentation/Swift/Codable] 协议时，您可以使用路径的 [codable](NavigationPath/codable.zh-Hans.md) 属性来获取路径的可序列化表示。使用该表示来保存和恢复栈的内容。例如，您可以定义一个 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 来处理路径的序列化和反序列化：

```swift
class MyModelObject: ObservableObject {
    @Published var path: NavigationPath

    static func readSerializedData() -> Data? {
        // Read data representing the path from app's persistent storage.
    }

    static func writeSerializedData(_ data: Data) {
        // Write data representing the path to app's persistent storage.
    }

    init() {
        if let data = Self.readSerializedData() {
            do {
                let representation = try JSONDecoder().decode(
                    NavigationPath.CodableRepresentation.self,
                    from: data)
                self.path = NavigationPath(representation)
            } catch {
                self.path = NavigationPath()
            }
        } else {
            self.path = NavigationPath()
        }
    }

    func save() {
        guard let representation = path.codable else { return }
        do {
            let encoder = JSONEncoder()
            let data = try encoder.encode(representation)
            Self.writeSerializedData(data)
        } catch {
            // Handle error.
        }
    }
}
```

然后，在视图中使用该对象，当 [Scene](Scene.zh-Hans.md) 进入 [background](ScenePhase/background.zh-Hans.md) 状态时，您可以保存导航路径的状态：

```swift
@StateObject private var pathState = MyModelObject()
@Environment(\.scenePhase) private var scenePhase

var body: some View {
    NavigationStack(path: $pathState.path) {
        // Add a root view here.
    }
    .onChange(of: scenePhase) { phase in
        if phase == .background {
            pathState.save()
        }
    }
}
```

## 创建导航路径

- **init()**：创建一个新的空导航路径。

- **init(_:)**：从可序列化的版本创建新的导航路径。

## 管理路径内容

- **isEmpty**：一个布尔值，指示此路径是否为空。

- **count**：此路径中的元素数量。

- **append(_:)**：将一个新的可编码值附加到此路径的末尾。

- **removeLast(_:)**：从此路径的末尾移除值。

## 路径编码

- **codable**：以可序列化格式描述此路径内容的值。

- **NavigationPath.CodableRepresentation**：导航路径的可序列化表示。

## 单列堆叠视图

- **NavigationStack**：显示根视图并允许您在根视图之上显示其他视图的视图。

- **navigationDestination(for:destination:)**：将目标视图与显示的数据类型关联起来，以便在导航堆栈中使用。

- **navigationDestination(isPresented:destination:)**：将目标视图与一个绑定关联起来，该绑定可用于将视图推送到 [NavigationStack](NavigationStack.zh-Hans.md)。

- **navigationDestination(item:destination:)**：将目标视图与一个绑定值关联起来，以便在导航堆栈或导航拆分视图中使用。

## 符合以下规范

- 可复制

- 可等效


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationPath
crawled: 2025-12-02T17:29:30Z
---

# NavigationPath

**Structure**

A type-erased list of data representing the content of a navigation stack.

## Declaration

```swift
struct NavigationPath
```

## Overview

You can manage the state of a [NavigationStack](NavigationStack.zh-Hans.md) by initializing the stack with a binding to a collection of data. The stack stores data items in the collection for each view on the stack. You also can read and write the collection to observe and alter the stack’s state.

When a stack displays views that rely on only one kind of data, you can use a standard collection, like an array, to hold the data. If you need to present different kinds of data in a single stack, use a navigation path instead. The path uses type erasure so you can manage a collection of heterogeneous elements. The path also provides the usual collection controls for adding, counting, and removing data elements.

### Serialize the path

When the values you present on the navigation stack conform to the [doc://com.apple.documentation/documentation/Swift/Codable] protocol, you can use the path’s [codable](NavigationPath/codable.zh-Hans.md) property to get a serializable representation of the path. Use that representation to save and restore the contents of the stack. For example, you can define an [doc://com.apple.documentation/documentation/Combine/ObservableObject] that handles serializing and deserializing the path:

```swift
class MyModelObject: ObservableObject {
    @Published var path: NavigationPath

    static func readSerializedData() -> Data? {
        // Read data representing the path from app's persistent storage.
    }

    static func writeSerializedData(_ data: Data) {
        // Write data representing the path to app's persistent storage.
    }

    init() {
        if let data = Self.readSerializedData() {
            do {
                let representation = try JSONDecoder().decode(
                    NavigationPath.CodableRepresentation.self,
                    from: data)
                self.path = NavigationPath(representation)
            } catch {
                self.path = NavigationPath()
            }
        } else {
            self.path = NavigationPath()
        }
    }

    func save() {
        guard let representation = path.codable else { return }
        do {
            let encoder = JSONEncoder()
            let data = try encoder.encode(representation)
            Self.writeSerializedData(data)
        } catch {
            // Handle error.
        }
    }
}
```

Then, using that object in your view, you can save the state of the navigation path when the [Scene](Scene.zh-Hans.md) enters the [background](ScenePhase/background.zh-Hans.md) state:

```swift
@StateObject private var pathState = MyModelObject()
@Environment(\.scenePhase) private var scenePhase

var body: some View {
    NavigationStack(path: $pathState.path) {
        // Add a root view here.
    }
    .onChange(of: scenePhase) { phase in
        if phase == .background {
            pathState.save()
        }
    }
}
```

## Creating a navigation path

- **init()**: Creates a new, empty navigation path.
- **init(_:)**: Creates a new navigation path from a serializable version.

## Managing path contents

- **isEmpty**: A Boolean that indicates whether this path is empty.
- **count**: The number of elements in this path.
- **append(_:)**: Appends a new codable value to the end of this path.
- **removeLast(_:)**: Removes values from the end of this path.

## Encoding a path

- **codable**: A value that describes the contents of this path in a serializable format.
- **NavigationPath.CodableRepresentation**: A serializable representation of a navigation path.

## Stacking views in one column

- **NavigationStack**: A view that displays a root view and enables you to present additional views over the root view.
- **navigationDestination(for:destination:)**: Associates a destination view with a presented data type for use within a navigation stack.
- **navigationDestination(isPresented:destination:)**: Associates a destination view with a binding that can be used to push the view onto a [NavigationStack](NavigationStack.zh-Hans.md).
- **navigationDestination(item:destination:)**: Associates a destination view with a bound value for use within a navigation stack or navigation split view

## Conforms To

- Copyable
- Equatable

