---
来源： https://developer.apple.com/documentation/SwiftUI/Model-data
抓取时间： 2025-12-02T17:32:27Z
---

# 模型数据

**API 收集**

管理应用程序用于驱动其界面的数据。

## 概览

SwiftUI 为用户界面设计提供了一种声明式方法。当您组成视图层次结构时，您还会指出视图的数据依赖关系。当数据因外部事件或用户执行的操作而发生变化时，SwiftUI 会自动更新界面中受影响的部分。因此，框架会自动执行视图控制器传统上所做的大部分工作。



框架提供了状态变量和绑定等工具，用于将应用程序的数据连接到用户界面。这些工具可以帮助您为应用程序中的每项数据维护一个单一的真实来源，部分原因是减少了您编写的胶合逻辑的数量。选择最适合您需要执行的任务的工具：

- 通过将值类型封装为[State](State.zh-Hans.md)属性，在视图中本地管理瞬态 UI 状态。
- 使用[Binding](Binding.zh-Hans.md) 属性封装器共享对真实源（如本地状态）的引用。
- 通过将[doc://com.apple.documentation/documentation/Observation/Observable()] 宏应用到模型数据类型，在视图中连接并观察引用模型数据。使用 [State](State.zh-Hans.md) 属性在视图中直接实例化可观察的模型数据类型。使用[Environment](Environment.zh-Hans.md) 属性包装器与层次结构中的其他视图共享可观察模型数据，而无需传递引用。

### 利用属性包装器

SwiftUI 实现了许多数据管理类型，如[State](State.zh-Hans.md) 和[Binding](Binding.zh-Hans.md)，作为 Swift 属性包装器。应用属性包装器的方法是在属性声明中添加一个带有包装器名称的属性。

```swift
@State private var isVisible = true // Declares isVisible as a state variable.
```

属性将获得包装器指定的行为。SwiftUI 中的状态和数据流属性包装器会监视数据的变化，并在必要时自动更新受影响的视图。当您在代码中直接引用属性时，您将访问封装后的值，上例中的`isVisible` 状态属性就是存储的布尔值。

```swift
if isVisible == true {
    Text("Hello") // Only renders when isVisible is true.
}
```

或者，您也可以在属性名称前加上美元符号 (`$`)，从而访问属性包装器的预测值。SwiftUI 状态和数据流属性包装器会投射一个[Binding](Binding.zh-Hans.md)，这是与包装值的双向连接，允许另一个视图访问和更改单个真实源。

```swift
Toggle("Visible", isOn: $isVisible) // The toggle can update the stored value.
```

有关属性包装器的更多信息，请参阅 [https://swift.org/documentation/#the-swift-programming-language] 中的 [https://docs.swift.org/swift-book/LanguageGuide/Properties.html#ID617]。

## 创建和共享视图状态

- 管理用户界面状态**：在应用程序的视图层次结构中封装特定于视图的数据，使视图可重复使用。
- **State**：一种属性封装类型，可读写由 SwiftUI 管理的值。
- **Bindable**：一种属性包装器类型，支持为可观察对象的可变属性创建绑定。
- **Binding**：一种属性包装器类型，可读取和写入真实源所拥有的值。

## 创建模型数据

- 在应用程序中管理模型数据**：在应用程序的数据模型和视图之间建立连接。
- 从 Observable Object 协议迁移到 Observable 宏**：更新您的现有应用程序，以充分利用 Swift 中观察的优势。
- **Observable()**：定义并实现 Observable 协议的一致性。
- 监控应用程序中的数据变化**：通过使用可观察对象，在应用程序的用户界面中显示数据的变化。
- **StateObject**：一种属性封装类型，用于实例化可观察对象。
- **ObservedObject**：一种属性封装类型，用于订阅一个可观察对象，并在该可观察对象发生变化时使视图失效。
- **ObservableObject**：一种具有发布器的对象类型，它会在对象发生变化之前发出。

## 响应数据变化

- **onChange(of:initial:_:)**：为该视图添加一个修改器，在特定值发生变化时触发一个操作。
- **onReceive(_:perform:)**：添加当该视图检测到指定发布者发布的数据时要执行的操作。

## 在整个应用程序中分发模型数据

- **environmentObject(_:)**：为视图的层次结构提供一个可观察对象。
- **environmentObject(_:)**：为视图子层次结构提供一个`ObservableObject`。
- **EnvironmentObject**：父视图或祖先视图提供的可观察对象的属性包装类型。

### 管理动态数据

- **DynamicProperty**：用于更新视图外部属性的存储变量接口。

## 数据和存储

- **环境值**：使用环境在整个视图层次结构中共享数据。
- **Preferences**：显示从视图到其容器视图的配置首选项。
- 持久存储**：跨应用程序会话存储数据。


---
source: https://developer.apple.com/documentation/SwiftUI/Model-data
crawled: 2025-12-02T17:32:27Z
---

# Model data

**API Collection**

Manage the data that your app uses to drive its interface.

## Overview

SwiftUI offers a declarative approach to user interface design. As you compose a hierarchy of views, you also indicate data dependencies for the views. When the data changes, either due to an external event or because of an action that the user performs, SwiftUI automatically updates the affected parts of the interface. As a result, the framework automatically performs most of the work that view controllers traditionally do.



The framework provides tools, like state variables and bindings, for connecting your app’s data to the user interface. These tools help you maintain a single source of truth for every piece of data in your app, in part by reducing the amount of glue logic you write. Select the tool that best suits the task you need to perform:

- Manage transient UI state locally within a view by wrapping value types as [State](State.zh-Hans.md) properties.
- Share a reference to a source of truth, like local state, using the [Binding](Binding.zh-Hans.md) property wrapper.
- Connect to and observe reference model data in views by applying the [doc://com.apple.documentation/documentation/Observation/Observable()] macro to the model data type. Instantiate an observable model data type directly in a view using a [State](State.zh-Hans.md) property. Share the observable model data with other views in the hierarchy without passing a reference using the [Environment](Environment.zh-Hans.md) property wrapper.

### Leveraging property wrappers

SwiftUI implements many data management types, like [State](State.zh-Hans.md) and [Binding](Binding.zh-Hans.md), as Swift property wrappers. Apply a property wrapper by adding an attribute with the wrapper’s name to a property’s declaration.

```swift
@State private var isVisible = true // Declares isVisible as a state variable.
```

The property gains the behavior that the wrapper specifies. The state and data flow property wrappers in SwiftUI watch for changes in your data, and automatically update affected views as necessary. When you refer directly to the property in your code, you access the wrapped value, which for the `isVisible` state property in the example above is the stored Boolean.

```swift
if isVisible == true {
    Text("Hello") // Only renders when isVisible is true.
}
```

Alternatively, you can access a property wrapper’s projected value by prefixing the property name with the dollar sign (`$`). SwiftUI state and data flow property wrappers project a [Binding](Binding.zh-Hans.md), which is a two-way connection to the wrapped value, allowing another view to access and mutate a single source of truth.

```swift
Toggle("Visible", isOn: $isVisible) // The toggle can update the stored value.
```

For more information about property wrappers, see [https://docs.swift.org/swift-book/LanguageGuide/Properties.html#ID617] in [https://swift.org/documentation/#the-swift-programming-language].

## Creating and sharing view state

- **Managing user interface state**: Encapsulate view-specific data within your app’s view hierarchy to make your views reusable.
- **State**: A property wrapper type that can read and write a value managed by SwiftUI.
- **Bindable**: A property wrapper type that supports creating bindings to the mutable properties of observable objects.
- **Binding**: A property wrapper type that can read and write a value owned by a source of truth.

## Creating model data

- **Managing model data in your app**: Create connections between your app’s data model and views.
- **Migrating from the Observable Object protocol to the Observable macro**: Update your existing app to leverage the benefits of Observation in Swift.
- **Observable()**: Defines and implements conformance of the Observable protocol.
- **Monitoring data changes in your app**: Show changes to data in your app’s user interface by using observable objects.
- **StateObject**: A property wrapper type that instantiates an observable object.
- **ObservedObject**: A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.
- **ObservableObject**: A type of object with a publisher that emits before the object has changed.

## Responding to data changes

- **onChange(of:initial:_:)**: Adds a modifier for this view that fires an action when a specific value changes.
- **onReceive(_:perform:)**: Adds an action to perform when this view detects data emitted by the given publisher.

## Distributing model data throughout your app

- **environmentObject(_:)**: Supplies an observable object to a view’s hierarchy.
- **environmentObject(_:)**: Supplies an `ObservableObject` to a view subhierarchy.
- **EnvironmentObject**: A property wrapper type for an observable object that a parent or ancestor view supplies.

## Managing dynamic data

- **DynamicProperty**: An interface for a stored variable that updates an external property of a view.

## Data and storage

- **Environment values**: Share data throughout a view hierarchy using the environment.
- **Preferences**: Indicate configuration preferences from views to their container views.
- **Persistent storage**: Store data for use across sessions of your app.

