---
来源： https://developer.apple.com/documentation/SwiftUI/ObservedObject/init(wrappedValue:)
抓取时间：2025-12-02T21:00:21Z
---

# init(wrappedValue:)

**Initializer**

创建具有初始包装值的观察对象。

## 声明

```swift
@MainActor @preconcurrency init(wrappedValue: ObjectType)
```

## 参数

- **wrappedValue**：可观测对象的初始值。

## 讨论

不要直接调用这个初始化器。相反，可以使用`@ObservedObject` 属性为视图声明一个输入，并在实例化视图时为该输入传递一个值。与管理数据存储的[StateObject](../StateObject.zh-Hans.md) 不同，您可以使用观察对象来引用您在其他地方管理的存储，如下面的示例：

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

在 `MySubView` 中显式调用观察对象初始化程序的行为是正确的，但每次 SwiftUI 调用视图初始化程序重绘视图时，都会不必要地重新创建相同的观察对象实例。

## 创建观察对象

- **init(initialValue:)**：创建具有初始值的观察对象。


---
source: https://developer.apple.com/documentation/SwiftUI/ObservedObject/init(wrappedValue:)
crawled: 2025-12-02T21:00:21Z
---

# init(wrappedValue:)

**Initializer**

Creates an observed object with an initial wrapped value.

## Declaration

```swift
@MainActor @preconcurrency init(wrappedValue: ObjectType)
```

## Parameters

- **wrappedValue**: An initial value for the observable object.

## Discussion

Don’t call this initializer directly. Instead, declare an input to a view with the `@ObservedObject` attribute, and pass a value to this input when you instantiate the view. Unlike a [StateObject](../StateObject.zh-Hans.md) which manages data storage, you use an observed object to refer to storage that you manage elsewhere, as in the following example:

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

Explicitly calling the observed object initializer in `MySubView` would behave correctly, but would needlessly recreate the same observed object instance every time SwiftUI calls the view’s initializer to redraw the view.

## Creating an observed object

- **init(initialValue:)**: Creates an observed object with an initial value.

