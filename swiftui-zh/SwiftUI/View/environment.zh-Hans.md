--- 来源：https://developer.apple.com/documentation/SwiftUI/View/environment(_:_:)

抓取时间：2025-11-30T21:17:28Z

---

# environment(_:_:)

**实例方法**

将指定键路径的环境值设置为给定值。

## 声明

```swift
nonisolated func environment<V>(_ keyPath: WritableKeyPath<EnvironmentValues, V>, _ value: V) -> some View

```

## 参数

- **keyPath**：一个键路径，指示要更新的 [EnvironmentValues](../EnvironmentValues.zh-Hans.md) 结构的属性。

- **value**：要为 `keyPath` 指定的项设置的新值。

## 返回值

一个视图，其环境已设置给定值。

## 讨论

使用此修饰符可以设置 [EnvironmentValues](../EnvironmentValues.zh-Hans.md) 结构的可写属性之一，包括您创建的自定义值。例如，您可以设置与 [truncationMode](../EnvironmentValues/truncationMode.zh-Hans.md) 键关联的值：

```swift
MyView()
    .environment(\.truncationMode, .head)
```

然后，您可以使用 [Environment](../Environment.zh-Hans.md) 属性包装器读取 `MyView` 或其子元素中的值：

```swift
struct MyView: View {
    @Environment(\.truncationMode) var truncationMode: Text.TruncationMode

    var body: some View { ... }
}
```

SwiftUI 提供了专用的视图修饰符来设置大多数环境值，例如 [truncationMode(_:)](truncationMode.zh-Hans.md) 修饰符，它可以设置 [truncationMode](../EnvironmentValues/truncationMode.zh-Hans.md) 的值：

```swift
MyView()
    .truncationMode(.head)
```

如果可用，请优先使用专用修饰符；定义自定义环境值时，请使用您自己的修饰符，如 [Entry()](../Entry.zh-Hans.md) 中所述。

此修饰符会影响指定的视图及其所有子视图。它对调用它的视图层级结构之外的视图无效。

## 修改视图的环境

- **environment(_:)**：将一个可观察对象放置在视图的环境中。

- **transformEnvironment(_:transform:)**：使用给定的函数转换指定键路径的环境值。


---
source: https://developer.apple.com/documentation/SwiftUI/View/environment(_:_:)
crawled: 2025-11-30T21:17:28Z
---

# environment(_:_:)

**Instance Method**

Sets the environment value of the specified key path to the given value.

## Declaration

```swift
nonisolated func environment<V>(_ keyPath: WritableKeyPath<EnvironmentValues, V>, _ value: V) -> some View

```

## Parameters

- **keyPath**: A key path that indicates the property of the [EnvironmentValues](../EnvironmentValues.zh-Hans.md) structure to update.
- **value**: The new value to set for the item specified by `keyPath`.

## Return Value

A view that has the given value set in its environment.

## Discussion

Use this modifier to set one of the writable properties of the [EnvironmentValues](../EnvironmentValues.zh-Hans.md) structure, including custom values that you create. For example, you can set the value associated with the [truncationMode](../EnvironmentValues/truncationMode.zh-Hans.md) key:

```swift
MyView()
    .environment(\.truncationMode, .head)
```

You then read the value inside `MyView` or one of its descendants using the [Environment](../Environment.zh-Hans.md) property wrapper:

```swift
struct MyView: View {
    @Environment(\.truncationMode) var truncationMode: Text.TruncationMode

    var body: some View { ... }
}
```

SwiftUI provides dedicated view modifiers for setting most environment values, like the [truncationMode(_:)](truncationMode.zh-Hans.md) modifier which sets the [truncationMode](../EnvironmentValues/truncationMode.zh-Hans.md) value:

```swift
MyView()
    .truncationMode(.head)
```

Prefer the dedicated modifier when available, and offer your own when defining custom environment values, as described in [Entry()](../Entry.zh-Hans.md).

This modifier affects the given view, as well as that view’s descendant views. It has no effect outside the view hierarchy on which you call it.

## Modifying the environment of a view

- **environment(_:)**: Places an observable object in the view’s environment.
- **transformEnvironment(_:transform:)**: Transforms the environment value of the specified key path with the given function.

