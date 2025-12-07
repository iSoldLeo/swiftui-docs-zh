--- 来源：https://developer.apple.com/documentation/SwiftUI/Environment/init(_:)

抓取时间：2025-12-01T10:56:04Z

---

# init(_:)

**Initializer**

创建一个环境属性，用于读取指定的键路径。

## 声明

```swift
init(_ keyPath: KeyPath<EnvironmentValues, Value>)
```

## 参数

- **keyPath**：指向特定结果值的键路径。

## 说明

请勿直接调用此初始化器。请改用属性包装器 [Environment](../Environment.zh-Hans.md) 声明属性，并提供该属性应反映的环境值的键路径：

```swift
struct MyView: View {
    @Environment(\.colorScheme) var colorScheme: ColorScheme

    // ...
}
```

当关联的环境值发生更改时，SwiftUI 会自动更新依赖于该属性的 `MyView` 部分。您无法使用这样的属性来修改环境值。要为视图层次结构设置值，请使用视图修饰符 [environment(_:_:)](../View/environment.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/Environment/init(_:)
crawled: 2025-12-01T10:56:04Z
---

# init(_:)

**Initializer**

Creates an environment property to read the specified key path.

## Declaration

```swift
init(_ keyPath: KeyPath<EnvironmentValues, Value>)
```

## Parameters

- **keyPath**: A key path to a specific resulting value.

## Discussion

Don’t call this initializer directly. Instead, declare a property with the [Environment](../Environment.zh-Hans.md) property wrapper, and provide the key path of the environment value that the property should reflect:

```swift
struct MyView: View {
    @Environment(\.colorScheme) var colorScheme: ColorScheme

    // ...
}
```

SwiftUI automatically updates any parts of `MyView` that depend on the property when the associated environment value changes. You can’t modify the environment value using a property like this. Instead, use the [environment(_:_:)](../View/environment.zh-Hans.md) view modifier on a view to set a value for a view hierarchy.

