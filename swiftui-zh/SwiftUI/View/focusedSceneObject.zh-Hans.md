--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusedSceneObject(_:)

抓取时间：2025-12-02T17:43:13Z

---

# focusedSceneObject(_:)

**实例方法**

创建一个新视图，该视图将提供的对象暴露给其他视图，这些视图的状态依赖于当前激活的场景。

## 声明

```swift
nonisolated func focusedSceneObject<T>(_ object: T) -> some View where T : ObservableObject

```

## 参数

- **object**：要与场景关联的可观察对象。

## 返回值

一个在场景激活时提供可观察对象的视图。

## 说明

对于无论焦点位于活动场景的哪个位置都必须可见的可观察对象，请使用此方法代替 [focusedObject(_:)](focusedObject.zh-Hans.md)。有时，主菜单和可发现性 HUD 命令等需要用到此功能，它们会观察并更新活动场景的数据，但并不关心用户实际关注的内容。场景的根视图可以提供场景的状态对象：

```swift
struct RootView: View {
    @StateObject private var sceneData = SceneData()

    var body: some View {
        NavigationSplitView {
            ...
        }
        .focusedSceneObject(sceneData)
    }
}
```

感兴趣的视图随后可以使用 [FocusedObject](../FocusedObject.zh-Hans.md) 属性包装器来观察和更新活动场景的状态对象。在本例中，应用程序命令会更新活动场景的数据，只要有任何场景处于活动状态，该命令就会启用。

```swift
struct MessageCommands: Commands {
    @FocusedObject private var sceneData: SceneData?

    var body: some Commands {
        CommandGroup(after: .newItem) {
            Button("New Message") {
                sceneData?.addMessage()
            }
            .keyboardShortcut("n", modifiers: [.option, .command])
            .disabled(sceneData == nil)
        }
    }
}
```

## 向焦点视图公开引用类型

- **focusedObject(_:)**：创建一个新视图，将提供的对象公开给其他视图，这些视图的状态依赖于焦点视图的层次结构。

- **FocusedObject**：焦点视图或其祖先视图提供的可观察对象的属性包装器类型。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusedSceneObject(_:)
crawled: 2025-12-02T17:43:13Z
---

# focusedSceneObject(_:)

**Instance Method**

Creates a new view that exposes the provided object to other views whose whose state depends on the active scene.

## Declaration

```swift
nonisolated func focusedSceneObject<T>(_ object: T) -> some View where T : ObservableObject

```

## Parameters

- **object**: The observable object to associate with the scene.

## Return Value

A view that supplies an observable object while the scene is active.

## Discussion

Use this method instead of [focusedObject(_:)](focusedObject.zh-Hans.md) for observable objects that must be visible regardless of where focus is located in the active scene. This is sometimes needed for things like main menu and discoverability HUD commands that observe and update data from the active scene but aren’t concerned with what the user is actually focused on. The scene’s root view can supply the scene’s state object:

```swift
struct RootView: View {
    @StateObject private var sceneData = SceneData()

    var body: some View {
        NavigationSplitView {
            ...
        }
        .focusedSceneObject(sceneData)
    }
}
```

Interested views can then use the [FocusedObject](../FocusedObject.zh-Hans.md) property wrapper to observe and update the active scene’s state object. In this example, an app command updates the active scene’s data, and is enabled as long as any scene is active.

```swift
struct MessageCommands: Commands {
    @FocusedObject private var sceneData: SceneData?

    var body: some Commands {
        CommandGroup(after: .newItem) {
            Button("New Message") {
                sceneData?.addMessage()
            }
            .keyboardShortcut("n", modifiers: [.option, .command])
            .disabled(sceneData == nil)
        }
    }
}
```

## Exposing reference types to focused views

- **focusedObject(_:)**: Creates a new view that exposes the provided object to other views whose whose state depends on the focused view hierarchy.
- **FocusedObject**: A property wrapper type for an observable object supplied by the focused view or one of its ancestors.

