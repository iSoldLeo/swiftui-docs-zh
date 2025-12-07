---
来源： https://developer.apple.com/documentation/SwiftUI/ContainerValues/subscript(_:)
抓取时间： 2025-12-01T11:31:04Z
---

# 下标(_:)

**实例下标**

访问与自定义键关联的特定容器值。

## 声明

```swift
subscript<Key>(key: Key.Type) -> Key.Value where Key : ContainerValueKey { get set }
```

## 概览

通过在容器值结构的扩展中声明一个新属性，并将[Entry()](../Entry.zh-Hans.md) 宏应用到变量声明中，创建自定义容器值：

```swift
extension ContainerValues {
    @Entry var myCustomValue: String = "Default value"
}
```宏

使用自定义容器值的方法与使用系统提供的值相同，即使用[containerValue(_:_:)](../View/containerValue.zh-Hans.md) 视图修饰符设置值，并从`subviews` 修饰符提供的[Subview](../Subview.zh-Hans.md) 中读取值。您还可以提供专用的视图修改器，以方便设置值：

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        containerValue(\.myCustomValue, myCustomValue)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ContainerValues/subscript(_:)
crawled: 2025-12-01T11:31:04Z
---

# subscript(_:)

**Instance Subscript**

Accesses the particular container value associated with a custom key.

## Declaration

```swift
subscript<Key>(key: Key.Type) -> Key.Value where Key : ContainerValueKey { get set }
```

## Overview

Create a custom container value by declaring a new property in an extension to the container values structure and applying the [Entry()](../Entry.zh-Hans.md) macro to the variable declaration:

```swift
extension ContainerValues {
    @Entry var myCustomValue: String = "Default value"
}
```

You use custom container values the same way you use system-provided values, setting a value with the [containerValue(_:_:)](../View/containerValue.zh-Hans.md) view modifier, and reading values from a [Subview](../Subview.zh-Hans.md) provided by the `subviews` modifier. You can also provide a dedicated view modifier as a convenience for setting the value:

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        containerValue(\.myCustomValue, myCustomValue)
    }
}
```

