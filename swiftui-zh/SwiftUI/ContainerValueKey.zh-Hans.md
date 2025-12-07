---
来源： https://developer.apple.com/documentation/SwiftUI/ContainerValueKey
抓取时间： 2025-12-02T17:40:12Z
---

# ContainerValueKey

**Protocol**

用于访问容器值的键。

## 声明

```swift
protocol ContainerValueKey
```

## 概览

通过使用新属性扩展[ContainerValues](ContainerValues.zh-Hans.md) 结构，可以创建自定义容器值。首先声明一个新的容器值键类型，并为所需的[defaultValue](ContainerValueKey/defaultValue.zh-Hans.md) 属性指定一个值：

```swift
private struct MyContainerValueKey: ContainerValueKey {
    static let defaultValue: String = "Default value"
}
```

Swift 编译器会自动将相关的 [Value](ContainerValueKey/Value.zh-Hans.md) 类型推断为您为默认值指定的类型。然后使用该键定义新的容器值属性：

```swift
extension ContainerValues {
    var myCustomValue: String {
        get { self[MyContainerValueKey.self] }
        set { self[MyContainerValueKey.self] = newValue }
    }
}
```

容器值的客户端永远不会直接使用键。相反，它们会使用自定义容器值属性的键路径。要为视图设置容器值，请向该视图添加 [containerValue(_:_:)](View/containerValue.zh-Hans.md) 视图修饰符：

```swift
MyView()
    .containerValue(\.myCustomValue, "Another string")
```

为了方便起见，您还可以定义一个专用的视图修改器来应用此容器值：

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        containerValue(\.myCustomValue, myCustomValue)
}
```

这样可以提高调用站点的清晰度：

```swift
MyView()
    .myCustomValue("Another string")
```

要读取容器值，请在包含视图上使用 `Group(subviews:)`，然后在该集合的成员上访问容器值。

```swift
@ViewBuilder var content: some View {
    Text("A").myCustomValue("Hello")
    Text("B").myCustomValue("World")
}

Group(subviews: content) { subviews in
    ForEach(subviews) { subview in
        Text(subview.containerValues.myCustomValue)
    }
}
```

在实践中，包含多个其他视图的视图大多会使用这种方法来从它们的子视图中提取信息。您可以将上面的示例转化为这样一个容器视图，如下所示：

```swift
struct MyContainer<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        Group(subviews: content) { subviews in
            ForEach(subviews) { subview in
                // Display each view side-by-side with its custom value.
                HStack {
                    subview
                    Text(subview.containerValues.myCustomValue)
                }
            }
        }
    }
}
```

## 关联类型

- **Value**：容器值产生的值的类型。

### 类型属性

- **defaultValue**：容器值的默认值。

## 访问容器的子视图

- **Subview**：表示另一个视图的子视图的不透明值。
- **SubviewsCollection**：表示视图子视图的不透明集合。
- **SubviewsCollectionSlice**：SubviewsCollection 的一个片段。
- **containerValue(_:_:)**：设置视图的特定容器值。
- **ContainerValues**：与给定视图关联的容器值的集合。


---
source: https://developer.apple.com/documentation/SwiftUI/ContainerValueKey
crawled: 2025-12-02T17:40:12Z
---

# ContainerValueKey

**Protocol**

A key for accessing container values.

## Declaration

```swift
protocol ContainerValueKey
```

## Overview

You can create custom container values by extending the [ContainerValues](ContainerValues.zh-Hans.md) structure with new properties. First declare a new container value key type and specify a value for the required [defaultValue](ContainerValueKey/defaultValue.zh-Hans.md) property:

```swift
private struct MyContainerValueKey: ContainerValueKey {
    static let defaultValue: String = "Default value"
}
```

The Swift compiler automatically infers the associated [Value](ContainerValueKey/Value.zh-Hans.md) type as the type you specify for the default value. Then use the key to define a new container value property:

```swift
extension ContainerValues {
    var myCustomValue: String {
        get { self[MyContainerValueKey.self] }
        set { self[MyContainerValueKey.self] = newValue }
    }
}
```

Clients of your container value never use the key directly. Instead, they use the key path of your custom container value property. To set the container value for a view, add the [containerValue(_:_:)](View/containerValue.zh-Hans.md) view modifier to that view:

```swift
MyView()
    .containerValue(\.myCustomValue, "Another string")
```

As a convenience, you can also define a dedicated view modifier to apply this container value:

```swift
extension View {
    func myCustomValue(_ myCustomValue: String) -> some View {
        containerValue(\.myCustomValue, myCustomValue)
}
```

This improves clarity at the call site:

```swift
MyView()
    .myCustomValue("Another string")
```

To read the container value, use `Group(subviews:)` on a containing view, and then access the container value on members of that collection.

```swift
@ViewBuilder var content: some View {
    Text("A").myCustomValue("Hello")
    Text("B").myCustomValue("World")
}

Group(subviews: content) { subviews in
    ForEach(subviews) { subview in
        Text(subview.containerValues.myCustomValue)
    }
}
```

In practice, this will mostly be used by views that contain multiple other views to extract information from their subviews. You could turn the example above into such a container view as follows:

```swift
struct MyContainer<Content: View>: View {
    var content: Content

    init(@ViewBuilder content: () -> Content) {
        self.content = content()
    }

    var body: some View {
        Group(subviews: content) { subviews in
            ForEach(subviews) { subview in
                // Display each view side-by-side with its custom value.
                HStack {
                    subview
                    Text(subview.containerValues.myCustomValue)
                }
            }
        }
    }
}
```

## Associated Types

- **Value**: The type of value produced by the container value.

## Type Properties

- **defaultValue**: The default value of the container value.

## Accessing a container’s subviews

- **Subview**: An opaque value representing a subview of another view.
- **SubviewsCollection**: An opaque collection representing the subviews of view.
- **SubviewsCollectionSlice**: A slice of a SubviewsCollection.
- **containerValue(_:_:)**: Sets a particular container value of a view.
- **ContainerValues**: A collection of container values associated with a given view.

