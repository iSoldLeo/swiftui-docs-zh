---
来源： https://developer.apple.com/documentation/swiftui/observedobject
抓取时间： 2025-12-04T13:07:53Z
---

# 观察对象

**Structure**

一种属性包装器类型，用于订阅可观察对象，并在可观察对象发生变化时使视图无效。

## 声明

```swift
@MainActor @propertyWrapper @preconcurrency @frozen struct ObservedObject<ObjectType> where ObjectType : ObservableObject
```

## 概览

当输入是[doc://com.apple.documentation/documentation/Combine/ObservableObject]，且您希望在对象的发布属性发生变化时更新视图时，将`@ObservedObject`属性添加到 SwiftUI [View](View.zh-Hans.md) 的参数中。通常这样做是为了将[StateObject](StateObject.zh-Hans.md) 传递到子视图中。

下面的示例将数据模型定义为可观察对象，在视图中将模型实例化为状态对象，然后将实例作为观察对象传递给子视图：

```swift
class DataModel: ObservableObject {
    @Published var name = "Some Name"
    @Published var isEnabled = false
}

struct MyView: View {
    @StateObject private var model = DataModel()

    var body: some View {
        Text(model.name)
        MySubView(model: model)
    }
}

struct MySubView: View {
    @ObservedObject var model: DataModel

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```

当可观察对象的任何已发布属性发生变化时，SwiftUI 会更新依赖于该对象的任何视图。子视图还可以对模型属性进行更新，如上例中的[Toggle](Toggle.zh-Hans.md)，这些更新会传播到整个视图层次结构中的其他观察者。

不要为观察对象指定默认值或初始值。该属性仅用于作为视图输入的属性，如上例。



## 创建观察对象

- **init(wrappedValue:)**：创建具有初始包装值的观察对象。
- **init(initialValue:)**：创建具有初始值的观察对象。

## 获取值

- **wrappedValue**：观察对象引用的基础值。
- **projectedValue**：被观测对象的投影，用于创建与其属性的绑定。
- **ObservedObject.Wrapper**：底层可观察对象的包装器，可创建与其属性的绑定。

### 创建模型数据

- 在应用程序中管理模型数据**：在应用程序的数据模型和视图之间建立连接。
- 从 Observable Object 协议迁移到 Observable 宏**：更新您的现有应用程序，以充分利用 Swift 中观察的优势。
- **Observable()**：定义并实现 Observable 协议的一致性。
- 监控应用程序中的数据变化**：通过使用可观察对象，在应用程序的用户界面中显示数据的变化。
- **StateObject**：一种属性封装类型，用于实例化可观察对象。
- **ObservableObject**：一种具有发布器的对象类型，发布器会在对象发生变化之前发出信号。

## 符合

- 动态属性
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/swiftui/observedobject
crawled: 2025-12-04T13:07:53Z
---

# ObservedObject

**Structure**

A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.

## Declaration

```swift
@MainActor @propertyWrapper @preconcurrency @frozen struct ObservedObject<ObjectType> where ObjectType : ObservableObject
```

## Overview

Add the `@ObservedObject` attribute to a parameter of a SwiftUI [View](View.zh-Hans.md) when the input is an [doc://com.apple.documentation/documentation/Combine/ObservableObject] and you want the view to update when the object’s published properties change. You typically do this to pass a [StateObject](StateObject.zh-Hans.md) into a subview.

The following example defines a data model as an observable object, instantiates the model in a view as a state object, and then passes the instance to a subview as an observed object:

```swift
class DataModel: ObservableObject {
    @Published var name = "Some Name"
    @Published var isEnabled = false
}

struct MyView: View {
    @StateObject private var model = DataModel()

    var body: some View {
        Text(model.name)
        MySubView(model: model)
    }
}

struct MySubView: View {
    @ObservedObject var model: DataModel

    var body: some View {
        Toggle("Enabled", isOn: $model.isEnabled)
    }
}
```

When any published property of the observable object changes, SwiftUI updates any view that depends on the object. Subviews can also make updates to the model properties, like the [Toggle](Toggle.zh-Hans.md) in the above example, that propagate to other observers throughout the view hierarchy.

Don’t specify a default or initial value for the observed object. Use the attribute only for a property that acts as an input for a view, as in the above example.



## Creating an observed object

- **init(wrappedValue:)**: Creates an observed object with an initial wrapped value.
- **init(initialValue:)**: Creates an observed object with an initial value.

## Getting the value

- **wrappedValue**: The underlying value that the observed object references.
- **projectedValue**: A projection of the observed object that creates bindings to its properties.
- **ObservedObject.Wrapper**: A wrapper of the underlying observable object that can create bindings to its properties.

## Creating model data

- **Managing model data in your app**: Create connections between your app’s data model and views.
- **Migrating from the Observable Object protocol to the Observable macro**: Update your existing app to leverage the benefits of Observation in Swift.
- **Observable()**: Defines and implements conformance of the Observable protocol.
- **Monitoring data changes in your app**: Show changes to data in your app’s user interface by using observable objects.
- **StateObject**: A property wrapper type that instantiates an observable object.
- **ObservableObject**: A type of object with a publisher that emits before the object has changed.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

