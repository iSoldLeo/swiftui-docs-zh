--- 来源：https://developer.apple.com/documentation/SwiftUI/View/containerValue(_:_:)

抓取时间：2025-12-02T17:23:22Z

---

# containerValue(_:_:)

**实例方法**

设置视图的特定容器值。

## 声明

```swift
nonisolated func containerValue<V>(_ keyPath: WritableKeyPath<ContainerValues, V>, _ value: V) -> some View

```

## 参数

- **keyPath**：一个键路径，指示要更新的 [ContainerValues](../ContainerValues.zh-Hans.md) 结构的属性。

- **value**：要为 `keyPath` 指定的项设置的新值。

## 返回值

一个视图，其 containerValues 中已设置给定值。

## 讨论

使用此修饰符可以设置 [ContainerValues](../ContainerValues.zh-Hans.md) 结构的可写属性之一，包括您创建的自定义值。

与首选项类似，容器值可以被其所在视图之上的视图读取。但是，与首选项不同的是，容器值没有合并行为，因为它们不会跳出其最近的容器。在以下示例中，容器值设置在包含视图上，但当它到达包含视图 [VStack](../VStack.zh-Hans.md) 时会被丢弃。

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

即使堆栈只有一个子视图，容器值仍然无法在 `VStack` 之外读取。即使容器只有一个子视图，容器值也不会跳出容器。

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

然而，在下一个例子中，包装视图 `VStack` 意味着 `Text` 视图不是外部容器的直接子视图，因此该容器无法读取已更改的值：

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

容器值修饰符也可用于修改容器值的可变子字段。

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

这允许您将多个相关的容器值分组到结构体中，同时为每个值维护单独的修饰符。

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

## 访问容器的子视图

- **Subview**：表示另一个视图的子视图的不透明值。

- **SubviewsCollection**：表示视图子视图的不透明集合。

- **SubviewsCollectionSlice**：SubviewsCollection 的一个切片。

- **ContainerValues**：与给定视图关联的容器值的集合。

- **ContainerValueKey**：用于访问容器值的键。


---
source: https://developer.apple.com/documentation/SwiftUI/View/containerValue(_:_:)
crawled: 2025-12-02T17:23:22Z
---

# containerValue(_:_:)

**Instance Method**

Sets a particular container value of a view.

## Declaration

```swift
nonisolated func containerValue<V>(_ keyPath: WritableKeyPath<ContainerValues, V>, _ value: V) -> some View

```

## Parameters

- **keyPath**: A key path that indicates the property of the [ContainerValues](../ContainerValues.zh-Hans.md) structure to update.
- **value**: The new value to set for the item specified by `keyPath`.

## Return Value

A view that has the given value set in its containerValues.

## Discussion

Use this modifier to set one of the writable properties of the [ContainerValues](../ContainerValues.zh-Hans.md) structure, including custom values that you create.

Like preferences, container values are able to be read by views above the view they’re set on. Unlike preferences, however, container values don’t have merging behavior because they don’t escape their closest container. In the following example, the container value is set on the contained view, but is dropped when it reaches the containing [VStack](../VStack.zh-Hans.md).

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

The container values modifier can also be used to modify mutable subfields of container values.

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

## Accessing a container’s subviews

- **Subview**: An opaque value representing a subview of another view.
- **SubviewsCollection**: An opaque collection representing the subviews of view.
- **SubviewsCollectionSlice**: A slice of a SubviewsCollection.
- **ContainerValues**: A collection of container values associated with a given view.
- **ContainerValueKey**: A key for accessing container values.

