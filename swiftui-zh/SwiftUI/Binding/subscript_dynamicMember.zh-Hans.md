---
来源： https://developer.apple.com/documentation/SwiftUI/Binding/subscript(dynamicMember:)
抓取时间： 2025-12-01T10:55:44Z
---

# subscript(dynamicMember:)

**实例下标**

返回与给定键路径的结果值的绑定。

## 声明

```swift
subscript<Subject>(dynamicMember keyPath: WritableKeyPath<Value, Subject>) -> Binding<Subject> { get }
```

## 参数

- **keyPath**：指向特定结果值的关键路径。

## 返回值

一个新的绑定。

## 概览

使用动态成员查找功能，将绑定的封装值属性从关键路径投射到新绑定中。返回值是从原始绑定中读取并写入的。当视图接受的绑定类型只与现有绑定中的一个值的属性相匹配时，这种方法就非常有用。

例如，`PlayerView` 使用`Slider` 控制一集节目的当前位置，并使用`Toggle` 控制该集节目是否是最爱。该视图将`currentPosition` 和`isFavorite` 属性投射到`Episode` 的绑定中，这些视图中的每个视图都使用动态成员查找功能接受这些绑定。

```swift
struct Episode {
    var title: LocalizedStringKey
    var duration: TimeInterval
    var currentPosition: TimeInterval
    var isFavorite: Bool
}

struct PlayerView: View {
    @Binding var episode: Episode

    var body: some View {
        Text(episode.title)
        Toggle("Favorite", isOn: $episode.isFavorite)
        Slider(
            value: $episode.currentPosition,
            in: 0...episode.duration
        )
    }
}
```

## 获取值

- **wrappedValue**：绑定变量引用的基础值。
- **projectedValue**：绑定值的投影，返回一个绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/subscript(dynamicMember:)
crawled: 2025-12-01T10:55:44Z
---

# subscript(dynamicMember:)

**Instance Subscript**

Returns a binding to the resulting value of a given key path.

## Declaration

```swift
subscript<Subject>(dynamicMember keyPath: WritableKeyPath<Value, Subject>) -> Binding<Subject> { get }
```

## Parameters

- **keyPath**: A key path to a specific resulting value.

## Return Value

A new binding.

## Overview

Use dynamic member lookup to project a property of the binding’s wrapped value from a key path into a new binding. The returned value is read from, and written to, the original binding. This can be useful when a view accepts a binding for a type that only matches a property of a value from an existing binding.

For example, the `PlayerView` controls the current position for an episode using a `Slider`, and whether the episode is a favorite using a `Toggle`. The view projects the `currentPosition` and `isFavorite` properties of `Episode` into bindings that each of these views accept using dynamic member lookup.

```swift
struct Episode {
    var title: LocalizedStringKey
    var duration: TimeInterval
    var currentPosition: TimeInterval
    var isFavorite: Bool
}

struct PlayerView: View {
    @Binding var episode: Episode

    var body: some View {
        Text(episode.title)
        Toggle("Favorite", isOn: $episode.isFavorite)
        Slider(
            value: $episode.currentPosition,
            in: 0...episode.duration
        )
    }
}
```

## Getting the value

- **wrappedValue**: The underlying value referenced by the binding variable.
- **projectedValue**: A projection of the binding value that returns a binding.

