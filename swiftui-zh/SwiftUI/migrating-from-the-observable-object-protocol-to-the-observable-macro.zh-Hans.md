--- 来源：https://developer.apple.com/documentation/swiftui/migrating-from-the-observable-object-protocol-to-the-observable-macro

抓取时间：2025-12-04T18:54:31Z

---

# 从 Observable Object 协议迁移到 Observable 宏

**示例代码**

更新您的现有应用，以利用 Swift 中 Observation 的优势。

## 概述

从 iOS 17、iPadOS 17、macOS 14、tvOS 17 和 watchOS 10 开始，SwiftUI 提供对 [doc://com.apple.documentation/documentation/Observation] 的支持，这是一个 Swift 特有的观察者设计模式实现。采用 Observation 可为您的应用带来以下优势：

- 跟踪可选值和对象集合，而使用 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 则无法实现这一点。 - 使用现有的数据流原语，例如 [State](State.zh-Hans.md) 和 [Environment](Environment.zh-Hans.md)，而不是基于对象的等效原语，例如 [StateObject](StateObject.zh-Hans.md) 和 [EnvironmentObject](EnvironmentObject.zh-Hans.md)。

- 基于视图的 [body-8kl5o](View/body-8kl5o.zh-Hans.md) 读取的可观察属性的变化来更新视图，而不是基于可观察对象发生的任何属性变化，这有助于提高应用程序的性能。

为了在您的应用程序中利用这些优势，您将学习如何将依赖于 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 的现有源代码替换为利用 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏的代码。

### 使用 Observable 宏

要在现有应用中采用 [doc://com.apple.documentation/documentation/Observation]，首先需要将数据模型类型中的 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 替换为 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏。[doc://com.apple.documentation/documentation/Observation/Observable()] 宏会在编译时生成源代码，为该类型添加观察支持。

然后，从可观察属性中移除 [doc://com.apple.documentation/documentation/Combine/Published] 属性包装器。观察功能不需要属性包装器即可使属性可观察。属性是否可观察取决于其相对于观察者（例如视图）的可访问性。

如果您有一些观察者可以访问但您不想跟踪的属性，请将 [doc://com.apple.documentation/documentation/Observation/ObservationIgnored()] 宏应用于该属性。

### 逐步迁移

您无需在整个应用中全面替换 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议。您可以逐步进行更改。首先，将一种数据模型类型更改为使用 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏。您的应用可以混合使用使用不同观察系统的数据模型类型。但是，SwiftUI 会根据数据模型类型使用的观察系统（`Observable` 或 `ObservableObject`）以不同的方式跟踪更改。

您可能会注意到，根据跟踪方法的不同，应用的行为略有差异。例如，当使用 [doc://com.apple.documentation/documentation/Observation/Observable()] 跟踪时，SwiftUI 仅在可观察属性更改且视图的 [body-8kl5o](View/body-8kl5o.zh-Hans.md) 直接读取该属性时才会更新视图。如果可观察属性未通过 `body` 读取，则视图不会更新。相反，当使用 `ObservableObject` 进行跟踪时，即使视图没有读取到更改的属性，只要 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 实例的任何已发布属性发生更改，视图也会更新。

### 迁移其他源代码

目前对示例应用程序所做的唯一更改是将 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏应用于 `Library` 并移除对 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 协议的支持。该应用程序仍然使用 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 数据流原语（例如 [StateObject](StateObject.zh-Hans.md)）来管理 `Library` 的实例。如果您构建并运行该应用程序，SwiftUI 仍会按预期更新视图。这是因为数据流属性包装器（例如 [StateObject](StateObject.zh-Hans.md) 和 [EnvironmentObject](EnvironmentObject.zh-Hans.md)）支持使用 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏的类型。SwiftUI 提供此支持，以便应用程序可以逐步更改源代码。

但是，要完全采用 [doc://com.apple.documentation/documentation/Observation]，请在更新数据模型类型后，将 [StateObject](StateObject.zh-Hans.md) 替换为 [State](State.zh-Hans.md)。例如，在以下代码中，主应用程序结构创建了一个 `Library` 的实例，并将其存储为 `StateObject`。它还使用 [environmentObject(_:)](View/environmentObject.zh-Hans.md) 修饰符将 `Library` 实例添加到环境中。

```swift
// BEFORE
@main
struct BookReaderApp: App {
    @StateObject private var library = Library()

    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environmentObject(library)
        }
    }
}
```

由于 `Library` 不再符合 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 规范，代码可以修改为使用 [State](State.zh-Hans.md) 代替 [StateObject](StateObject.zh-Hans.md)，并使用 [environment(_:)](View/environment.zh-Hans.md) 修饰符将 `library` 添加到环境中。

```swift
// AFTER
@main
struct BookReaderApp: App {
    @State private var library = Library()

    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(library)
        }
    }
}
```

在 `Library` 完全采用 [doc://com.apple.documentation/documentation/Observation] 规范之前，还需要进行一项更改。此前，视图 `LibraryView` 使用 [EnvironmentObject](EnvironmentObject.zh-Hans.md) 属性包装器从环境中检索 `Library` 实例。然而，新代码使用的是 [Environment](Environment.zh-Hans.md) 属性包装器。

### 移除 ObservedObject 属性包装器

为了完成示例应用程序的迁移，请将数据模型类型 `Book` 更改为支持 [doc://com.apple.documentation/documentation/Observation]，方法是从类型声明中移除 [doc://com.apple.documentation/documentation/Combine/ObservableObject] 并应用 [doc://com.apple.documentation/documentation/Observation/Observable()] 宏。然后，从可观察属性中移除 [doc://com.apple.documentation/documentation/Combine/Published] 属性包装器。

接下来，从 `BookView` 中的 `book` 变量中移除 [ObservedObject](ObservedObject.zh-Hans.md) 属性包装器。采用 [doc://com.apple.documentation/documentation/Observation] 时，不需要此属性包装器。这是因为 SwiftUI 会自动跟踪视图直接读取的任何可观察属性。例如，当 `book.title` 发生变化时，SwiftUI 会更新 `BookView`。

但是，如果视图需要绑定到可观察类型，请将 [ObservedObject](ObservedObject.zh-Hans.md) 替换为 [Bindable](Bindable.zh-Hans.md) 属性包装器。此属性包装器提供对可观察类型的绑定支持，以便需要绑定的视图可以更改可观察属性。例如，在以下代码中，[TextField](TextField.zh-Hans.md) 接收到对 `book.title` 的绑定：

## 创建模型数据

- **管理应用中的模型数据**：创建应用数据模型和视图之间的连接。

- **Observable()**：定义并实现 Observable 协议的一致性。

- **监控应用中的数据变化**：使用可观察对象在应用的用户界面中显示数据变化。

- **StateObject**：一种属性包装器类型，用于实例化可观察对象。

- **ObservedObject**：一种属性包装器类型，用于订阅可观察对象，并在可观察对象发生变化时使视图失效。

- **ObservableObject**：一种带有发布者的对象类型，该发布者会在对象发生变化之前发出消息。


---
source: https://developer.apple.com/documentation/swiftui/migrating-from-the-observable-object-protocol-to-the-observable-macro
crawled: 2025-12-04T18:54:31Z
---

# Migrating from the Observable Object protocol to the Observable macro

**Sample Code**

Update your existing app to leverage the benefits of Observation in Swift.

## Overview

Starting with iOS 17, iPadOS 17, macOS 14, tvOS 17, and watchOS 10, SwiftUI provides support for [doc://com.apple.documentation/documentation/Observation], a Swift-specific implementation of the observer design pattern. Adopting Observation provides your app with the following benefits:

- Tracking optionals and collections of objects, which isn’t possible when using [doc://com.apple.documentation/documentation/Combine/ObservableObject].
- Using existing data flow primitives like [State](State.zh-Hans.md) and [Environment](Environment.zh-Hans.md) instead of object-based equivalents such as [StateObject](StateObject.zh-Hans.md) and [EnvironmentObject](EnvironmentObject.zh-Hans.md).
- Updating views based on changes to the observable properties that a view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md) reads instead of any property changes that occur to an observable object, which can help improve your app’s performance.

To take advantage of these benefits in your app, you’ll discover how to replace existing source code that relies on [doc://com.apple.documentation/documentation/Combine/ObservableObject] with code that leverages the [doc://com.apple.documentation/documentation/Observation/Observable()] macro.



### Use the Observable macro

To adopt [doc://com.apple.documentation/documentation/Observation] in an existing app, begin by replacing [doc://com.apple.documentation/documentation/Combine/ObservableObject] in your data model type with the [doc://com.apple.documentation/documentation/Observation/Observable()] macro. The [doc://com.apple.documentation/documentation/Observation/Observable()] macro generates source code at compile time that adds observation support to the type.



Then remove the [doc://com.apple.documentation/documentation/Combine/Published] property wrapper from observable properties. Observation doesn’t require a property wrapper to make a property observable. Instead, the accessibility of the property in relationship to an observer, such as a view, determines whether a property is observable.



If you have properties that are accessible to an observer that you don’t want to track, apply the [doc://com.apple.documentation/documentation/Observation/ObservationIgnored()] macro to the property.

### Migrate incrementally

You don’t need to make a wholesale replacement of the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol throughout your app. Instead, you can make changes incrementally. Start by changing one data model type to use the [doc://com.apple.documentation/documentation/Observation/Observable()] macro. Your app can mix data model types that use different observation systems. However, SwiftUI tracks changes differently based on the observation system that a data model type uses, `Observable` versus `ObservableObject`.

You may notice slight behavioral differences in your app based on the tracking method. For instance, when tracking as [doc://com.apple.documentation/documentation/Observation/Observable()], SwiftUI updates a view only when an observable property changes and the view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md) reads the property directly. The view doesn’t update when observable properties not read by `body` changes. In contrast, a view updates when any published property of an [doc://com.apple.documentation/documentation/Combine/ObservableObject] instance changes, even if the view doesn’t read the property that changes, when tracking as `ObservableObject`.



### Migrate other source code

The only change made to the sample app so far is to apply the [doc://com.apple.documentation/documentation/Observation/Observable()] macro to `Library` and remove support for the [doc://com.apple.documentation/documentation/Combine/ObservableObject] protocol. The app still uses the [doc://com.apple.documentation/documentation/Combine/ObservableObject] data flow primitive like [StateObject](StateObject.zh-Hans.md) to manage an instance of `Library`. If you were to build and run the app, SwiftUI still updates the views as expected. That’s because data flow property wrappers such as [StateObject](StateObject.zh-Hans.md) and [EnvironmentObject](EnvironmentObject.zh-Hans.md) support types that use the [doc://com.apple.documentation/documentation/Observation/Observable()] macro. SwiftUI provides this support so apps can make source code changes incrementally.

However, to fully adopt [doc://com.apple.documentation/documentation/Observation], replace the use of [StateObject](StateObject.zh-Hans.md) with [State](State.zh-Hans.md) after updating your data model type. For example, in the following code the main app structure creates an instance of `Library` and stores it as a `StateObject`. It also adds the `Library` instance to the environment using the [environmentObject(_:)](View/environmentObject.zh-Hans.md) modifier.

```swift
// BEFORE
@main
struct BookReaderApp: App {
    @StateObject private var library = Library()

    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environmentObject(library)
        }
    }
}
```

Now that `Library` no longer conforms to [doc://com.apple.documentation/documentation/Combine/ObservableObject], the code can change to use [State](State.zh-Hans.md) instead of [StateObject](StateObject.zh-Hans.md) and to add `library` to the environment using the [environment(_:)](View/environment.zh-Hans.md) modifier.

```swift
// AFTER
@main
struct BookReaderApp: App {
    @State private var library = Library()

    var body: some Scene {
        WindowGroup {
            LibraryView()
                .environment(library)
        }
    }
}
```

One more change must happen before `Library` fully adopts [doc://com.apple.documentation/documentation/Observation]. Previously the view `LibraryView` retrieved a `Library` instance from the environment using the [EnvironmentObject](EnvironmentObject.zh-Hans.md) property wrapper. The new code, however, uses the [Environment](Environment.zh-Hans.md) property wrapper instead.



### Remove the ObservedObject property wrapper

To wrap up the migration of the sample app, change the data model type `Book` to support [doc://com.apple.documentation/documentation/Observation] by removing [doc://com.apple.documentation/documentation/Combine/ObservableObject] from the type declaration and apply the [doc://com.apple.documentation/documentation/Observation/Observable()] macro. Then remove the [doc://com.apple.documentation/documentation/Combine/Published] property wrapper from observable properties.



Next, remove the [ObservedObject](ObservedObject.zh-Hans.md) property wrapper from the `book` variable in the `BookView`. This property wrapper isn’t needed when adopting [doc://com.apple.documentation/documentation/Observation]. That’s because SwiftUI automatically tracks any observable properties that a view’s [body-8kl5o](View/body-8kl5o.zh-Hans.md) reads directly. For example, SwiftUI updates `BookView` when `book.title` changes.



However, if a view needs a binding to an observable type, replace [ObservedObject](ObservedObject.zh-Hans.md) with the [Bindable](Bindable.zh-Hans.md) property wrapper. This property wrapper provides binding support to an observable type so that views that expect a binding can change an observable property. For instance, in the following code [TextField](TextField.zh-Hans.md) receives a binding to `book.title`:



## Creating model data

- **Managing model data in your app**: Create connections between your app’s data model and views.
- **Observable()**: Defines and implements conformance of the Observable protocol.
- **Monitoring data changes in your app**: Show changes to data in your app’s user interface by using observable objects.
- **StateObject**: A property wrapper type that instantiates an observable object.
- **ObservedObject**: A property wrapper type that subscribes to an observable object and invalidates a view whenever the observable object changes.
- **ObservableObject**: A type of object with a publisher that emits before the object has changed.

