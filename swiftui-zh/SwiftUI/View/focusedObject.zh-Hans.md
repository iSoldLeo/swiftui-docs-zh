--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusedObject(_:)

抓取时间：2025-11-30T21:28:14Z

---

# focusedObject(_:)

**实例方法**

创建一个新视图，该视图将提供的对象暴露给其他视图，这些视图的状态依赖于当前聚焦的视图层级结构。

## 声明

```swift
nonisolated func focusedObject<T>(_ object: T) -> some View where T : ObservableObject

```

## 参数

- **object**：要与焦点关联的可观察对象。

## 返回值

一个在获得焦点时提供可观察对象的视图。

## 讨论

当场景包含多个可聚焦视图及其各自关联的数据，并且您需要一个应用程序或场景作用域的元素（例如命令或工具栏项）来操作当前聚焦视图关联的数据时，请使用此方法代替 [focusedSceneObject(_:)](focusedSceneObject.zh-Hans.md)。每个可聚焦视图都可以提供自己的对象：

```swift
struct MessageView: View {
    @StateObject private var message = Message(...)

    var body: some View {
        TextField(...)
            .focusedObject(message)
    }
}
```

感兴趣的视图随后可以使用 [FocusedObject](../FocusedObject.zh-Hans.md) 属性包装器来观察和更新聚焦视图的对象。在本例中，应用程序命令会更新聚焦视图的数据，并且当焦点位于场景中不相关的部分时，该命令会自动禁用：

```swift
struct MessageCommands: Commands {
    @FocusedObject private var message: Message?

    var body: some Commands {
        CommandGroup(after: .pasteboard) {
            Button("Add Duck to Message") {
                message?.text.append(" 🦆")
            }
            .keyboardShortcut("d")
            .disabled(message == nil)
        }
    }
}
```

## 向聚焦视图公开引用类型

- **focusedSceneObject(_:)**：创建一个新视图，该视图将提供的对象公开给其他视图，这些视图的状态依赖于活动场景。

- **FocusedObject**：用于包装由当前聚焦视图或其祖先视图提供的可观察对象的属性类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusedObject(_:)
crawled: 2025-11-30T21:28:14Z
---

# focusedObject(_:)

**Instance Method**

Creates a new view that exposes the provided object to other views whose whose state depends on the focused view hierarchy.

## Declaration

```swift
nonisolated func focusedObject<T>(_ object: T) -> some View where T : ObservableObject

```

## Parameters

- **object**: The observable object to associate with focus.

## Return Value

A view that supplies an observable object when in focus.

## Discussion

Use this method instead of [focusedSceneObject(_:)](focusedSceneObject.zh-Hans.md) when your scene includes multiple focusable views with their own associated data, and you need an app- or scene-scoped element like a command or toolbar item that operates on the data associated with whichever view currently has focus. Each focusable view can supply its own object:

```swift
struct MessageView: View {
    @StateObject private var message = Message(...)

    var body: some View {
        TextField(...)
            .focusedObject(message)
    }
}
```

Interested views can then use the [FocusedObject](../FocusedObject.zh-Hans.md) property wrapper to observe and update the focused view’s object. In this example, an app command updates the focused view’s data, and is automatically disabled when focus is in an unrelated part of the scene:

```swift
struct MessageCommands: Commands {
    @FocusedObject private var message: Message?

    var body: some Commands {
        CommandGroup(after: .pasteboard) {
            Button("Add Duck to Message") {
                message?.text.append(" 🦆")
            }
            .keyboardShortcut("d")
            .disabled(message == nil)
        }
    }
}
```

## Exposing reference types to focused views

- **focusedSceneObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the active scene.
- **FocusedObject**: A property wrapper type for an observable object supplied by the focused view or one of its ancestors.

