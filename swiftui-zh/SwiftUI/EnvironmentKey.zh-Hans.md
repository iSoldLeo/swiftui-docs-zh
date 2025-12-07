--- 来源：https://developer.apple.com/documentation/SwiftUI/EnvironmentKey
抓取时间：2025-12-02T17:32:22Z
---

# EnvironmentKey

**Protocol**

用于访问环境变量值的键。

## 声明

```swift
protocol EnvironmentKey
```

## 概述

您可以通过扩展 [EnvironmentValues](EnvironmentValues.zh-Hans.md) 结构并添加新属性来创建自定义环境变量值。首先声明一个新的环境变量键类型，并为所需的 [defaultValue](EnvironmentKey/defaultValue.zh-Hans.md) 属性指定一个值：

```swift
private struct MyEnvironmentKey: EnvironmentKey {
    static let defaultValue: String = "Default value"
}
```

Swift 编译器会自动将关联的 [Value](EnvironmentKey/Value.zh-Hans.md) 类型推断为您为默认值指定的类型。然后使用该键定义一个新的环境值属性：

```swift
extension EnvironmentValues {
    var myCustomValue: String {
        get { self[MyEnvironmentKey.self] }
        set { self[MyEnvironmentKey.self] = newValue }
    }
}
```

环境值的客户端不会直接使用该键。相反，它们会使用自定义环境值属性的键路径。要为视图及其所有子视图设置环境值，请将视图修饰符 [environment(_:_:)](View/environment.zh-Hans.md) 添加到该视图：

```swift
MyView()
    .environment(\.myCustomValue, "Another string")
```

为了方便起见，您还可以定义一个专用的视图修饰符来应用此环境值：

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        environment(\.myCustomValue, myCustomValue)
    }
}
```

这提高了调用点的清晰度：

```swift
MyView()
    .myCustomValue("Another string")
```

要从 `MyView` 或其子视图中读取值，请使用属性包装器 [Environment](Environment.zh-Hans.md)：

```swift
struct MyView: View {
    @Environment(\.myCustomValue) var customValue: String

    var body: some View {
        Text(customValue) // Displays "Another string".
    }
}
```

## 获取默认值

- **defaultValue**：环境键的默认值。

- **Value**：表示环境键值类型的关联类型。

## 创建自定义环境值

- **Entry()**：创建环境值、事务值、容器值或焦点值条目。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentKey
crawled: 2025-12-02T17:32:22Z
---

# EnvironmentKey

**Protocol**

A key for accessing values in the environment.

## Declaration

```swift
protocol EnvironmentKey
```

## Overview

You can create custom environment values by extending the [EnvironmentValues](EnvironmentValues.zh-Hans.md) structure with new properties. First declare a new environment key type and specify a value for the required [defaultValue](EnvironmentKey/defaultValue.zh-Hans.md) property:

```swift
private struct MyEnvironmentKey: EnvironmentKey {
    static let defaultValue: String = "Default value"
}
```

The Swift compiler automatically infers the associated [Value](EnvironmentKey/Value.zh-Hans.md) type as the type you specify for the default value. Then use the key to define a new environment value property:

```swift
extension EnvironmentValues {
    var myCustomValue: String {
        get { self[MyEnvironmentKey.self] }
        set { self[MyEnvironmentKey.self] = newValue }
    }
}
```

Clients of your environment value never use the key directly. Instead, they use the key path of your custom environment value property. To set the environment value for a view and all its subviews, add the [environment(_:_:)](View/environment.zh-Hans.md) view modifier to that view:

```swift
MyView()
    .environment(\.myCustomValue, "Another string")
```

As a convenience, you can also define a dedicated view modifier to apply this environment value:

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        environment(\.myCustomValue, myCustomValue)
    }
}
```

This improves clarity at the call site:

```swift
MyView()
    .myCustomValue("Another string")
```

To read the value from inside `MyView` or one of its descendants, use the [Environment](Environment.zh-Hans.md) property wrapper:

```swift
struct MyView: View {
    @Environment(\.myCustomValue) var customValue: String

    var body: some View {
        Text(customValue) // Displays "Another string".
    }
}
```

## Getting the default value

- **defaultValue**: The default value for the environment key.
- **Value**: The associated type representing the type of the environment key’s value.

## Creating custom environment values

- **Entry()**: Creates an environment values, transaction, container values, or focused values entry.

