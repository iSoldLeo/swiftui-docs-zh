--- 来源：https://developer.apple.com/documentation/SwiftUI/Scene/environment(_:_:)

抓取时间：2025-11-30T21:17:30Z

---

# environment(_:_:)

**实例方法**

将指定键路径的环境值设置为给定值。

## 声明

```swift
nonisolated func environment<V>(_ keyPath: WritableKeyPath<EnvironmentValues, V>, _ value: V) -> some Scene

```

## 参数

- **keyPath**：一个键路径，指示要更新的 [EnvironmentValues](../EnvironmentValues.zh-Hans.md) 结构的属性。

- **value**：要为 `keyPath` 指定的项设置的新值。

## 返回值

一个视图，其环境已设置给定值。

## 讨论

使用此修饰符可以设置 [EnvironmentValues](../EnvironmentValues.zh-Hans.md) 结构的可写属性之一，包括您创建的自定义值。例如，您可以创建一个自定义环境键 `styleOverrides` 来设置一个值，该值代表整个应用程序的样式设置：

```swift
WindowGroup {
    ContentView()
}
.environment(\.styleOverrides, StyleOverrides())
```

然后，您可以使用 [Environment](../Environment.zh-Hans.md) 属性包装器读取 `ContentView` 或其子结构中的值：

```swift
struct MyView: View {
    @Environment(\.styleOverrides) var styleOverrides: StyleOverrides

    var body: some View { ... }
}
```

此修饰符会影响给定的场景及其子视图。它对调用它的视图层次结构之外的视图没有影响。

## 修改场景的环境

- **environment(_:)**：将一个可观察对象放置在场景的环境中。

- **transformEnvironment(_:transform:)**：使用给定函数转换指定键路径的环境值。


---
source: https://developer.apple.com/documentation/SwiftUI/Scene/environment(_:_:)
crawled: 2025-11-30T21:17:30Z
---

# environment(_:_:)

**Instance Method**

Sets the environment value of the specified key path to the given value.

## Declaration

```swift
nonisolated func environment<V>(_ keyPath: WritableKeyPath<EnvironmentValues, V>, _ value: V) -> some Scene

```

## Parameters

- **keyPath**: A key path that indicates the property of the [EnvironmentValues](../EnvironmentValues.zh-Hans.md) structure to update.
- **value**: The new value to set for the item specified by `keyPath`.

## Return Value

A view that has the given value set in its environment.

## Discussion

Use this modifier to set one of the writable properties of the [EnvironmentValues](../EnvironmentValues.zh-Hans.md) structure, including custom values that you create. For example, you can create a custom environment key `styleOverrides` to set a value that represents style settings that for the entire app:

```swift
WindowGroup {
    ContentView()
}
.environment(\.styleOverrides, StyleOverrides())
```

You then read the value inside `ContentView` or one of its descendants using the [Environment](../Environment.zh-Hans.md) property wrapper:

```swift
struct MyView: View {
    @Environment(\.styleOverrides) var styleOverrides: StyleOverrides

    var body: some View { ... }
}
```

This modifier affects the given scene, as well as that scene’s descendant views. It has no effect outside the view hierarchy on which you call it.

## Modifying the environment of a scene

- **environment(_:)**: Places an observable object in the scene’s environment.
- **transformEnvironment(_:transform:)**: Transforms the environment value of the specified key path with the given function.

