---
来源： https://developer.apple.com/documentation/swiftui/binding
抓取时间： 2025-12-03T05:35:57Z
---

# 约束力

**Structure**

属性包装类型，可读写真实源拥有的值。

### 声明

```swift
@frozen @propertyWrapper @dynamicMemberLookup struct Binding<Value>
```

## 概览

使用绑定可在存储数据的属性与显示和更改数据的视图之间创建双向连接。绑定将一个属性与存储在其他地方的真相源连接起来，而不是直接存储数据。例如，在播放和暂停之间切换的按钮可以使用`Binding` 属性包装器创建与其父视图属性的绑定。

```swift
struct PlayButton: View {
    @Binding var isPlaying: Bool

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") {
            isPlaying.toggle()
        }
    }
}
```

父视图声明了一个属性来保存播放状态，并使用[State](State.zh-Hans.md) 属性包装器来表示该属性是值的真实来源。

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var isPlaying: Bool = false

    var body: some View {
        VStack {
            Text(episode.title)
                .foregroundStyle(isPlaying ? .primary : .secondary)
            PlayButton(isPlaying: $isPlaying) // Pass a binding.
        }
    }
}
```

当 `PlayerView` 初始化 `PlayButton` 时，它会将其状态属性的绑定传递到按钮的绑定属性中。将`$` 前缀应用于属性包装值会返回其 [projectedValue](State/projectedValue.zh-Hans.md)，对于状态属性包装器来说，会返回与该值的绑定。

每当用户点击 `PlayButton` 时，`PlayerView` 就会更新其 `isPlaying` 状态。

只有当绑定的封装值类型也符合`Sendable`时，绑定才符合`Sendable`。在不同并发域之间传递可发送绑定始终是安全的。但是，从不同并发域读取或写入绑定的封装值可能安全，也可能不安全，这取决于绑定是如何创建的。如果 SwiftUI 检测到绑定的使用方式可能危及数据安全，它将在运行时发出警告。



## 创建绑定

- **init(_:)**：通过将基值投影到哈希值来创建绑定。
- **init(projectedValue:)**：从另一个绑定的值创建一个绑定。
- **init(get:set:)**：使用读写绑定值的闭包创建绑定。
- **constant(_:)**：创建具有不可变值的绑定。

## 获取值

- **wrappedValue**：绑定变量引用的基础值。
- **projectedValue**：绑定值的投影，返回一个绑定。
- **subscript(dynamicMember:)**：返回给定键路径的绑定结果值。

## 管理更改

- **id**：与此实例关联的实体的稳定标识，对应于绑定的包装值的`id`。
- **animation(_:)**：指定绑定值发生变化时要执行的动画。
- **transaction(_:)**：指定绑定的事务。
- **transaction**：绑定的事务。

## 下标

- **subscript(_:)**

## 默认实现

- **可识别的实施**

## 创建和共享视图状态

- 管理用户界面状态**：在应用程序的视图层次结构中封装特定于视图的数据，使视图可重复使用。
- **State**：一种属性封装类型，可读写由 SwiftUI 管理的值。
- **Bindable**：一种属性包装器类型，支持为可观察对象的可变属性创建绑定。

## 符合

- 双向集合
- 集合
- 可复制
- 动态属性
- 可识别
- 随机访问集合
- 可发送
- 可发送元类型
- 序列


---
source: https://developer.apple.com/documentation/swiftui/binding
crawled: 2025-12-03T05:35:57Z
---

# Binding

**Structure**

A property wrapper type that can read and write a value owned by a source of truth.

## Declaration

```swift
@frozen @propertyWrapper @dynamicMemberLookup struct Binding<Value>
```

## Overview

Use a binding to create a two-way connection between a property that stores data, and a view that displays and changes the data. A binding connects a property to a source of truth stored elsewhere, instead of storing data directly. For example, a button that toggles between play and pause can create a binding to a property of its parent view using the `Binding` property wrapper.

```swift
struct PlayButton: View {
    @Binding var isPlaying: Bool

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") {
            isPlaying.toggle()
        }
    }
}
```

The parent view declares a property to hold the playing state, using the [State](State.zh-Hans.md) property wrapper to indicate that this property is the value’s source of truth.

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var isPlaying: Bool = false

    var body: some View {
        VStack {
            Text(episode.title)
                .foregroundStyle(isPlaying ? .primary : .secondary)
            PlayButton(isPlaying: $isPlaying) // Pass a binding.
        }
    }
}
```

When `PlayerView` initializes `PlayButton`, it passes a binding of its state property into the button’s binding property. Applying the `$` prefix to a property wrapped value returns its [projectedValue](State/projectedValue.zh-Hans.md), which for a state property wrapper returns a binding to the value.

Whenever the user taps the `PlayButton`, the `PlayerView` updates its `isPlaying` state.

A binding conforms to `Sendable` only if its wrapped value type also conforms to `Sendable`. It is always safe to pass a sendable binding between different concurrency domains. However, reading from or writing to a binding’s wrapped value from a different concurrency domain may or may not be safe, depending on how the binding was created. SwiftUI will issue a warning at runtime if it detects a binding being used in a way that may compromise data safety.



## Creating a binding

- **init(_:)**: Creates a binding by projecting the base value to a hashable value.
- **init(projectedValue:)**: Creates a binding from the value of another binding.
- **init(get:set:)**: Creates a binding with closures that read and write the binding value.
- **constant(_:)**: Creates a binding with an immutable value.

## Getting the value

- **wrappedValue**: The underlying value referenced by the binding variable.
- **projectedValue**: A projection of the binding value that returns a binding.
- **subscript(dynamicMember:)**: Returns a binding to the resulting value of a given key path.

## Managing changes

- **id**: The stable identity of the entity associated with this instance, corresponding to the `id` of the binding’s wrapped value.
- **animation(_:)**: Specifies an animation to perform when the binding value changes.
- **transaction(_:)**: Specifies a transaction for the binding.
- **transaction**: The binding’s transaction.

## Subscripts

- **subscript(_:)**

## Default Implementations

- **Identifiable Implementations**

## Creating and sharing view state

- **Managing user interface state**: Encapsulate view-specific data within your app’s view hierarchy to make your views reusable.
- **State**: A property wrapper type that can read and write a value managed by SwiftUI.
- **Bindable**: A property wrapper type that supports creating bindings to the mutable properties of observable objects.

## Conforms To

- BidirectionalCollection
- Collection
- Copyable
- DynamicProperty
- Identifiable
- RandomAccessCollection
- Sendable
- SendableMetatype
- Sequence

