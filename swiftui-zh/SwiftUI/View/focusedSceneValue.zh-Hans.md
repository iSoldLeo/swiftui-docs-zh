--- 来源：https://developer.apple.com/documentation/SwiftUI/View/focusedSceneValue(_:_:)

抓取时间：2025-12-02T17:43:10Z

---

# focusedSceneValue(_:_:)

**实例方法**

通过注入您提供的值来修改此视图，该值可供其他状态依赖于当前焦点场景的视图使用。

## 声明

```swift
nonisolated func focusedSceneValue<T>(_ keyPath: WritableKeyPath<FocusedValues, T?>, _ value: T) -> some View

```

## 参数

- **keyPath**：将 `value` 添加到已发布焦点值表时要关联的键路径。

- **value**：要发布的焦点值。

## 返回值

此视图的修改版本。

## 讨论

对于无论焦点位于活动场景的哪个位置都必须可见的值，请使用此方法代替 [focusedValue(_:_:)](focusedValue.zh-Hans.md)。例如，如果应用程序需要一个命令将焦点移动到侧边栏中的特定文本字段，则可以使用此修饰符发布一个按钮操作，只要场景处于活动状态，该操作就对命令视图可见，而与焦点位于场景中的哪个位置无关。

```swift
struct Sidebar: View {
    @FocusState var isFiltering: Bool

    var body: some View {
        VStack {
            TextField(...)
                .focused(when: $isFiltering)
                .focusedSceneValue(\.filterAction) {
                    isFiltering = true
                }
        }
    }
}

struct NavigationCommands: Commands {
    @FocusedValue(\.filterAction) var filterAction

    var body: some Commands {
        CommandMenu("Navigate") {
            Button("Filter in Sidebar") {
                filterAction?()
            }
        }
        .disabled(filterAction == nil)
    }
}

extension FocusedValues {
    @Entry var filterAction: (() -> Void)?
}
```

## 向焦点视图公开值类型

- **focusedValue(_:)**：设置给定对象类型的焦点值。

- **focusedValue(_:_:)**：通过注入您提供的值来修改此视图，供状态依赖于焦点视图层次结构的其他视图使用。

- **focusedSceneValue(_:)**：在场景范围内设置给定对象类型的焦点值。

- **FocusedValues**：当前聚焦的场景或视图及其祖先场景或视图导出的状态集合。


---
source: https://developer.apple.com/documentation/SwiftUI/View/focusedSceneValue(_:_:)
crawled: 2025-12-02T17:43:10Z
---

# focusedSceneValue(_:_:)

**Instance Method**

Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused scene.

## Declaration

```swift
nonisolated func focusedSceneValue<T>(_ keyPath: WritableKeyPath<FocusedValues, T?>, _ value: T) -> some View

```

## Parameters

- **keyPath**: The key path to associate `value` with when adding it to the existing table of published focus values.
- **value**: The focus value to publish.

## Return Value

A modified representation of this view.

## Discussion

Use this method instead of [focusedValue(_:_:)](focusedValue.zh-Hans.md) for values that must be visible regardless of where focus is located in the active scene. For example, if an app needs a command for moving focus to a particular text field in the sidebar, it could use this modifier to publish a button action that’s visible to command views as long as the scene is active, and regardless of where focus happens to be in it.

```swift
struct Sidebar: View {
    @FocusState var isFiltering: Bool

    var body: some View {
        VStack {
            TextField(...)
                .focused(when: $isFiltering)
                .focusedSceneValue(\.filterAction) {
                    isFiltering = true
                }
        }
    }
}

struct NavigationCommands: Commands {
    @FocusedValue(\.filterAction) var filterAction

    var body: some Commands {
        CommandMenu("Navigate") {
            Button("Filter in Sidebar") {
                filterAction?()
            }
        }
        .disabled(filterAction == nil)
    }
}

extension FocusedValues {
    @Entry var filterAction: (() -> Void)?
}
```

## Exposing value types to focused views

- **focusedValue(_:)**: Sets the focused value for the given object type.
- **focusedValue(_:_:)**: Modifies this view by injecting a value that you provide for use by other views whose state depends on the focused view hierarchy.
- **focusedSceneValue(_:)**: Sets the focused value for the given object type at a scene-wide scope.
- **FocusedValues**: A collection of state exported by the focused scene or view and its ancestors.

