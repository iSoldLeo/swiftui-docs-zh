--- 来源：https://developer.apple.com/documentation/SwiftUI/StateObject
抓取时间：2025-12-02T16:16:33Z

---

# StateObject

**Structure**

一种属性包装类型，用于实例化可观察对象。

## 声明

```swift
@MainActor @frozen @propertyWrapper @preconcurrency struct StateObject<ObjectType> where ObjectType : ObservableObject
```

## 概述

将状态对象用作存储在视图层次结构中的引用类型的唯一数据源。通过在属性声明中应用 `@StateObject` 特性并提供符合 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议的初始值，即可在 [App](App.zh-Hans.md)、[Scene](Scene.zh-Hans.md) 或 [View](View.zh-Hans.md) 中创建状态对象。将状态对象声明为私有，以防止通过成员初始化器设置它们，这可能会与 SwiftUI 提供的存储管理机制冲突：

```swift
class DataModel: ObservableObject {
    @Published var name = "Some Name"
    @Published var isEnabled = false
}

struct MyView: View {
    @StateObject private var model = DataModel() // Create the state object.

    var body: some View {
        Text(model.name) // Updates when the data model changes.
        MySubView()
            .environmentObject(model)
    }
}
```

SwiftUI 在声明状态对象的容器的生命周期内，只会创建一次模型对象的新实例。例如，如果视图的输入发生变化，SwiftUI 不会创建新实例；但如果视图的标识发生变化，则会创建新实例。当可观察对象的已发布属性发生变化时，SwiftUI 会更新任何依赖于这些属性的视图，例如上例中的 [Text](Text.zh-Hans.md) 视图。

### 与子视图共享状态对象

您可以通过具有 [ObservedObject](ObservedObject.zh-Hans.md) 特性的属性将状态对象传递给子视图。或者，通过将 [environmentObject(_:)](View/environmentObject.zh-Hans.md) 修饰符应用于视图（例如上述代码中的 `MySubView`），将对象添加到视图层次结构的环境中。然后，您可以使用 [EnvironmentObject](EnvironmentObject.zh-Hans.md) 属性在 `MySubView` 或其任何子视图中读取对象：

```swift
struct MySubView: View {
    @EnvironmentObject var model: DataModel

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```

使用美元符号 (`$`) 运算符获取状态对象属性的 [Binding](Binding.zh-Hans.md) 值。当您想要创建双向连接时，请使用绑定。在上述代码中，[Toggle](Toggle.zh-Hans.md) 通过绑定控制模型的 `isEnabled` 值。

### 使用外部数据初始化状态对象

当状态对象的初始状态依赖于来自容器外部的数据时，您可以在容器的初始化方法中显式调用该状态对象的初始化方法。例如，假设上例中的数据模型在初始化期间接收一个名为 `name` 的输入，而您希望使用来自视图外部的该名称的值。您可以通过在为视图创建的显式初始化方法中调用状态对象的初始化方法来实现这一点：

```swift
struct MyInitializableView: View {
    @StateObject private var model: DataModel

    init(name: String) {
        // SwiftUI ensures that the following initialization uses the
        // closure only once during the lifetime of the view, so
        // later changes to the view's name input have no effect.
        _model = StateObject(wrappedValue: DataModel(name: name))
    }

    var body: some View {
        VStack {
            Text("Name: \(model.name)")
        }
    }
}
```

请谨慎操作。SwiftUI 仅在给定视图中首次调用状态对象的初始化方法时才会对其进行初始化。这确保了即使视图的输入发生变化，该对象也能提供稳定的存储。但是，如果您显式初始化状态对象，则可能会导致意外行为或不必要的副作用。

在上面的例子中，如果 `name` 的输入值（指向 `MyInitializableView`）发生变化，SwiftUI 会使用新值重新运行视图的初始化器。但是，SwiftUI 只会在第一次调用状态对象的初始化器时运行你提供的自动闭包，因此模型中存储的 `name` 值不会改变。

当对象所依赖的外部数据在给定实例的容器中保持不变时，显式初始化状态对象效果很好。例如，你可以创建两个具有不同常量名称的视图：

```swift
var body: some View {
    VStack {
        MyInitializableView(name: "Ravi")
        MyInitializableView(name: "Maria")
    }
}
```

### 通过更改视图标识强制重新初始化

如果你希望 SwiftUI 在视图输入发生变化时重新初始化状态对象，请确保视图的标识也同时发生变化。一种方法是使用 [id(_:)](View/id.zh-Hans.md) 修饰符将视图的标识绑定到更改的值。例如，您可以确保当 `name` 输入更改时，`MyInitializableView` 实例的标识也随之更改：

```swift
MyInitializableView(name: name)
    .id(name) // Binds the identity of the view to the name property.
```

如果您需要视图根据多个值的更改重新初始化状态，可以使用 [doc://com.apple.documentation/documentation/Swift/Hasher] 将这些值合并为一个标识符。例如，如果您希望在 `name` 或 `isEnabled` 的值发生变化时更新 `MyInitializableView` 中的数据模型，您可以将这两个变量合并到一个哈希表中：

```swift
var hash: Int {
    var hasher = Hasher()
    hasher.combine(name)
    hasher.combine(isEnabled)
    return hasher.finalize()
}
```

然后将合并后的哈希表作为标识符应用到视图中：

```swift
MyInitializableView(name: name, isEnabled: isEnabled)
    .id(hash)
```

请注意，每次输入发生变化时重新初始化状态对象会带来性能开销。此外，更改视图标识可能会产生副作用。例如，如果视图标识同时发生变化，SwiftUI 不会自动为视图内部的变化添加动画效果。此外，更改标识会重置视图持有的*所有*状态，包括您管理的 [State](State.zh-Hans.md)、[FocusState](FocusState.zh-Hans.md)、[GestureState](GestureState.zh-Hans.md) 等值。

## 创建状态对象

- **init(wrappedValue:)**：创建一个带有初始包装值的新状态对象。

## 获取值

- **wrappedValue**：状态对象引用的底层值。

- **projectedValue**：状态对象的投影，用于创建与其属性的绑定。

## 创建模型数据

- **管理应用中的模型数据**：创建应用数据模型和视图之间的连接。

- **从 Observable Object 协议迁移到 Observable 宏**：更新现有应用，以利用 Swift 中 Observation 的优势。

- **Observable()**：定义并实现 Observable 协议的一致性。

- **监控应用中的数据更改**：使用 Observable 对象在应用的用户界面中显示数据更改。

- **ObservedObject**：一种属性包装器类型，它订阅一个可观察对象，并在该可观察对象发生更改时使视图失效。

- **ObservableObject**：一种带有发布者的对象类型，该发布者会在对象发生更改之前发出消息。

## 符合以下协议

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/StateObject
crawled: 2025-12-02T16:16:33Z
---

# StateObject

**Structure**

A property wrapper type that instantiates an observable object.

## Declaration

```swift
@MainActor @frozen @propertyWrapper @preconcurrency struct StateObject<ObjectType> where ObjectType : ObservableObject
```

## Overview

Use a state object as the single source of truth for a reference type that you store in a view hierarchy. Create a state object in an [App](App.zh-Hans.md), [Scene](Scene.zh-Hans.md), or [View](View.zh-Hans.md) by applying the `@StateObject` attribute to a property declaration and providing an initial value that conforms to the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol. Declare state objects as private to prevent setting them from a memberwise initializer, which can conflict with the storage management that SwiftUI provides:

```swift
class DataModel: ObservableObject {
    @Published var name = "Some Name"
    @Published var isEnabled = false
}

struct MyView: View {
    @StateObject private var model = DataModel() // Create the state object.

    var body: some View {
        Text(model.name) // Updates when the data model changes.
        MySubView()
            .environmentObject(model)
    }
}
```

SwiftUI creates a new instance of the model object only once during the lifetime of the container that declares the state object. For example, SwiftUI doesn’t create a new instance if a view’s inputs change, but does create a new instance if the identity of a view changes. When published properties of the observable object change, SwiftUI updates any view that depends on those properties, like the [Text](Text.zh-Hans.md) view in the above example.



### Share state objects with subviews

You can pass a state object into a subview through a property that has the [ObservedObject](ObservedObject.zh-Hans.md) attribute. Alternatively, add the object to the environment of a view hierarchy by applying the [environmentObject(_:)](View/environmentObject.zh-Hans.md) modifier to a view, like `MySubView` in the above code. You can then read the object inside `MySubView` or any of its descendants using the [EnvironmentObject](EnvironmentObject.zh-Hans.md) attribute:

```swift
struct MySubView: View {
    @EnvironmentObject var model: DataModel

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```

Get a [Binding](Binding.zh-Hans.md) to the state object’s properties using the dollar sign (`$`) operator. Use a binding when you want to create a two-way connection. In the above code, the [Toggle](Toggle.zh-Hans.md) controls the model’s `isEnabled` value through a binding.

### Initialize state objects using external data

When a state object’s initial state depends on data that comes from outside its container, you can call the object’s initializer explicitly from within its container’s initializer. For example, suppose the data model from the previous example takes a `name` input during initialization and you want to use a value for that name that comes from outside the view. You can do this with a call to the state object’s initializer inside an explicit initializer that you create for the view:

```swift
struct MyInitializableView: View {
    @StateObject private var model: DataModel

    init(name: String) {
        // SwiftUI ensures that the following initialization uses the
        // closure only once during the lifetime of the view, so
        // later changes to the view's name input have no effect.
        _model = StateObject(wrappedValue: DataModel(name: name))
    }

    var body: some View {
        VStack {
            Text("Name: \(model.name)")
        }
    }
}
```

Use caution when doing this. SwiftUI only initializes a state object the first time you call its initializer in a given view. This ensures that the object provides stable storage even as the view’s inputs change. However, it might result in unexpected behavior or unwanted side effects if you explicitly initialize the state object.

In the above example, if the `name` input to `MyInitializableView` changes, SwiftUI reruns the view’s initializer with the new value. However, SwiftUI runs the autoclosure that you provide to the state object’s initializer only the first time you call the state object’s initializer, so the model’s stored `name` value doesn’t change.

Explicit state object initialization works well when the external data that the object depends on doesn’t change for a given instance of the object’s container. For example, you can create two views with different constant names:

```swift
var body: some View {
    VStack {
        MyInitializableView(name: "Ravi")
        MyInitializableView(name: "Maria")
    }
}
```



### Force reinitialization by changing view identity

If you want SwiftUI to reinitialize a state object when a view input changes, make sure that the view’s identity changes at the same time. One way to do this is to bind the view’s identity to the value that changes using the [id(_:)](View/id.zh-Hans.md) modifier. For example, you can ensure that the identity of an instance of `MyInitializableView` changes when its `name` input changes:

```swift
MyInitializableView(name: name)
    .id(name) // Binds the identity of the view to the name property.
```



If you need the view to reinitialize state based on changes in more than one value, you can combine the values into a single identifier using a [doc://com.apple.documentation/documentation/Swift/Hasher]. For example, if you want to update the data model in `MyInitializableView` when the values of either `name` or `isEnabled` change, you can combine both variables into a single hash:

```swift
var hash: Int {
    var hasher = Hasher()
    hasher.combine(name)
    hasher.combine(isEnabled)
    return hasher.finalize()
}
```

Then apply the combined hash to the view as an identifier:

```swift
MyInitializableView(name: name, isEnabled: isEnabled)
    .id(hash)
```

Be mindful of the performance cost of reinitializing the state object every time the input changes. Also, changing view identity can have side effects. For example, SwiftUI doesn’t automatically animate changes inside the view if the view’s identity changes at the same time. Also, changing the identity resets *all* state held by the view, including values that you manage as [State](State.zh-Hans.md), [FocusState](FocusState.zh-Hans.md), [GestureState](GestureState.zh-Hans.md), and so on.

## Creating a state object

- **init(wrappedValue:)**: Creates a new state object with an initial wrapped value.

## Getting the value

- **wrappedValue**: The underlying value referenced by the state object.
- **projectedValue**: A projection of the state object that creates bindings to its properties.

## Creating model data

- **Managing model data in your app**: Create connections between your app’s data model and views.
- **Migrating from the Observable Object protocol to the Observable macro**: Update your existing app to leverage the benefits of Observation in Swift.
- **Observable()**: Defines and implements conformance of the Observable protocol.
- **Monitoring data changes in your app**: Show changes to data in your app’s user interface by using observable objects.
- **ObservedObject**: A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.
- **ObservableObject**: A type of object with a publisher that emits before the object has changed.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

