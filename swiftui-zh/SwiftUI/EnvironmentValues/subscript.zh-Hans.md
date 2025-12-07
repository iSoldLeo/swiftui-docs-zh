---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/subscript(_:)
抓取时间： 2025-12-03T06:07:05Z
---

# 下标(_:)

**实例下标**

访问与自定义键相关的环境值。

## 声明

```swift
subscript<K>(key: K.Type) -> K.Value where K : EnvironmentKey { get set }
```

## 概览

通过在环境值结构的扩展中声明一个新属性，并将[Entry()](../Entry.zh-Hans.md) 宏应用于变量声明，创建自定义环境值：

```swift
extension EnvironmentValues {
    @Entry var myCustomValue: String = "Default value"
}
```宏

使用自定义环境值的方式与使用系统提供的值相同，使用[environment(_:_:)](../View/environment.zh-Hans.md) 视图修饰符设置值，并使用[Environment](../Environment.zh-Hans.md) 属性包装器读取值。您也可以提供一个专用的视图修饰符，以方便设置值：

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        environment(\.myCustomValue, myCustomValue)
    }
}
```

## 创建和访问值

- **init()**：创建环境值实例。
- **description**：表示环境值实例内容的字符串。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/subscript(_:)
crawled: 2025-12-03T06:07:05Z
---

# subscript(_:)

**Instance Subscript**

Accesses the environment value associated with a custom key.

## Declaration

```swift
subscript<K>(key: K.Type) -> K.Value where K : EnvironmentKey { get set }
```

## Overview

Create a custom environment value by declaring a new property in an extension to the environment values structure and applying the [Entry()](../Entry.zh-Hans.md) macro to the variable declaration:

```swift
extension EnvironmentValues {
    @Entry var myCustomValue: String = "Default value"
}
```

You use custom environment values the same way you use system-provided values, setting a value with the [environment(_:_:)](../View/environment.zh-Hans.md) view modifier, and reading values with the [Environment](../Environment.zh-Hans.md) property wrapper. You can also provide a dedicated view modifier as a convenience for setting the value:

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        environment(\.myCustomValue, myCustomValue)
    }
}
```

## Creating and accessing values

- **init()**: Creates an environment values instance.
- **description**: A string that represents the contents of the environment values instance.

