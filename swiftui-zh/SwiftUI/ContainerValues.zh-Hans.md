--- 来源：https://developer.apple.com/documentation/SwiftUI/ContainerValues
抓取时间：2025-12-02T17:40:11Z

---

# ContainerValues

**Structure**

与给定视图关联的容器值集合。

## 声明

```swift
struct ContainerValues
```

## 概述

SwiftUI 在 `ContainerValues` 结构中公开与每个视图关联的值集合。

您在给定视图上设置的容器值仅影响该视图。与首选项类似，容器值可以被设置它们的视图之上的视图读取。但是，与首选项不同的是，容器值没有合并行为，因为它们不会跳出其最近的容器。在以下示例中，容器值在包含视图上设置，但当它到达包含视图 [VStack](VStack.zh-Hans.md) 时会被丢弃。 ```swift
VStack {
    Text("A")
        .containerValue(\.myCustomValue, 1) // myCustomValue = 1
    Text("B")
        .containerValue(\.myCustomValue, 2) // myCustomValue = 2
    // container values are unaffected by views that aren't containers:
    Text("C")
        .containerValue(\.myCustomValue, 3)
        .padding() // myCustomValue = 3
} // myCustomValue = its default value, values do not escape the container
```

即使栈只有一个子元素，容器的值仍然无法在 `VStack` 之外读取。即使容器只有一个子元素，容器的值也不会逃逸出容器。

在这个例子中，一个直接子视图写入了一个容器值，允许其直接容器视图读取该值：

```swift
@ViewBuilder var content: some View {
    Text("A")
        .containerValue(\.myCustomValue, 1)
}

ForEach(subviews: content) { subview in
    Text("value = \(subview.containerValues.myCustomValue)") // shows "value = 1"
}
```

然而，在下一个例子中，由于包装视图 `VStack` 的存在，`Text` 视图不再是外部容器的直接子视图，因此该容器无法读取已更改的值：

```swift
@ViewBuilder var containedContent: some View {
    VStack {
        Text("A")
            .containerValue(\.myCustomValue, 1)
    }
}

ForEach(subviews: containedContent) { subviews in
    Text("value = \(subview.containerValues.myCustomValue)") // shows the default value
}
```

要创建自定义容器值，可以在容器值结构的扩展中声明一个新属性，并将 [Entry()](Entry.zh-Hans.md) 宏应用于变量声明：

```swift
extension ContainerValues {
    @Entry var myCustomValue: String = "Default value"
}
```

然后，该值的客户端可以通过从 [Subview](Subview.zh-Hans.md) 的容器值集合中读取该值来访问它。

相关的容器配置也可以分组到同一个容器值键下。

```swift
struct PinPosition {
    var rotation: Double = 0
    var xOffset: Int = 0
}

extension ContainerValues {
    @Entry var pinPosition: PinPosition = .init()
}

// pinPosition.rotation = 0, pinPosition.xOffset = 3
Text("A").containerValue(\.pinPosition.xOffset, 3)

// pinPosition.rotation = 10, pinPosition.xOffset = 5
Text("B")
    .containerValue(\.pinPosition.rotation, 10)
    .containerValue(\.pinPosition.xOffset, 5)
```

此功能允许您将多个相关的容器值分组到结构体中，同时保留用于写入每个值的独立修饰符。

```swift
extension View {
    func pinRotation(_ rotation: Double) -> some View {
        containerValue(\.pinPosition.rotation, rotation)
    }

    func pinXOffset(_ xOffset: Int) -> some View {
        containerValue(\.pinPosition.xOffset, xOffset)
    }
}
```

## 实例方法

- **hasTag(_:)**：如果容器值包含与给定值匹配的标签，则返回 true。

- **tag(for:)**：如果容器值包含给定类型的标签，则返回该标签的值。

## 下标

- **subscript(_:)**：访问与自定义键关联的特定容器值。

## 访问容器的子视图

- **Subview**：表示另一个视图的子视图的不透明值。

- **SubviewsCollection**：表示视图的子视图的不透明集合。

- **SubviewsCollectionSlice**：子视图集合的一个切片。

- **containerValue(_:_:)**：设置视图的特定容器值。

- **ContainerValueKey**：用于访问容器值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/ContainerValues
crawled: 2025-12-02T17:40:11Z
---

# ContainerValues

**Structure**

A collection of container values associated with a given view.

## Declaration

```swift
struct ContainerValues
```

## Overview

SwiftUI exposes a collection of values associated with each view in the `ContainerValues` structure.

Container values you set on a given view affect only that view. Like preferences, container values are able to be read by views above the view they’re set on. Unlike preferences, however, container values don’t have merging behavior because they don’t escape their closest container. In the following example, the container value is set on the contained view, but is dropped when it reaches the containing [VStack](VStack.zh-Hans.md).

```swift
VStack {
    Text("A")
        .containerValue(\.myCustomValue, 1) // myCustomValue = 1
    Text("B")
        .containerValue(\.myCustomValue, 2) // myCustomValue = 2
    // container values are unaffected by views that aren't containers:
    Text("C")
        .containerValue(\.myCustomValue, 3)
        .padding() // myCustomValue = 3
} // myCustomValue = its default value, values do not escape the container
```

Even if a stack has only one child, container values still won’t be readable outside of the `VStack`. Container values don’t escape a container even if the container has only one child.

In this example, a direct subview writes a container value, allowing its direct container view to read it back:

```swift
@ViewBuilder var content: some View {
    Text("A")
        .containerValue(\.myCustomValue, 1)
}

ForEach(subviews: content) { subview in
    Text("value = \(subview.containerValues.myCustomValue)") // shows "value = 1"
}
```

However in the next example, the wrapping `VStack` means the `Text` view is not a direct subview of the outer container, so that container cannot read the changed value:

```swift
@ViewBuilder var containedContent: some View {
    VStack {
        Text("A")
            .containerValue(\.myCustomValue, 1)
    }
}

ForEach(subviews: containedContent) { subviews in
    Text("value = \(subview.containerValues.myCustomValue)") // shows the default value
}
```

Create a custom container value by declaring a new property in an extension to the container values structure and applying the [Entry()](Entry.zh-Hans.md) macro to the variable declaration:

```swift
extension ContainerValues {
    @Entry var myCustomValue: String = "Default value"
}
```

Clients of your value then access the value by reading it from the container values collection of a [Subview](Subview.zh-Hans.md).

Related pieces of container configuration can also be grouped under the same container values key.

```swift
struct PinPosition {
    var rotation: Double = 0
    var xOffset: Int = 0
}

extension ContainerValues {
    @Entry var pinPosition: PinPosition = .init()
}

// pinPosition.rotation = 0, pinPosition.xOffset = 3
Text("A").containerValue(\.pinPosition.xOffset, 3)

// pinPosition.rotation = 10, pinPosition.xOffset = 5
Text("B")
    .containerValue(\.pinPosition.rotation, 10)
    .containerValue(\.pinPosition.xOffset, 5)
```

This allows you to group multiple related container values into structs while maintaining separate modifiers to write each value.

```swift
extension View {
    func pinRotation(_ rotation: Double) -> some View {
        containerValue(\.pinPosition.rotation, rotation)
    }

    func pinXOffset(_ xOffset: Int) -> some View {
        containerValue(\.pinPosition.xOffset, xOffset)
    }
}
```

## Instance Methods

- **hasTag(_:)**: Returns true if the container values contain a tag matching a given value.
- **tag(for:)**: The tag value for the given type if the container values contains one.

## Subscripts

- **subscript(_:)**: Accesses the particular container value associated with a custom key.

## Accessing a container’s subviews

- **Subview**: An opaque value representing a subview of another view.
- **SubviewsCollection**: An opaque collection representing the subviews of view.
- **SubviewsCollectionSlice**: A slice of a SubviewsCollection.
- **containerValue(_:_:)**: Sets a particular container value of a view.
- **ContainerValueKey**: A key for accessing container values.

