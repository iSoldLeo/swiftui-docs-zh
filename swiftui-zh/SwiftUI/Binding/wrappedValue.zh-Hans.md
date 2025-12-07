---
来源： https://developer.apple.com/documentation/SwiftUI/Binding/wrappedValue
抓取时间： 2025-12-03T06:06:40Z
---

# wrappedValue

**实例属性**

绑定变量引用的底层值。

## 声明

```swift
var wrappedValue: Value { get nonmutating set }
```

## 讨论

该属性提供了对值数据的主要访问权限。但是，不能直接访问 `wrappedValue`。而是使用[Binding](../Binding.zh-Hans.md) 属性创建的属性变量。在下面的代码示例中，绑定变量 `isPlaying` 返回 `wrappedValue` 的值：

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

当可变绑定值发生变化时，新值会立即可用。但是，显示该值的视图的更新是异步进行的，因此视图可能不会立即显示更改。

## 获取值

- **projectedValue**：绑定值的投影，返回一个绑定。
- **subscript(dynamicMember:)**：返回给定键路径的绑定结果值。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/wrappedValue
crawled: 2025-12-03T06:06:40Z
---

# wrappedValue

**Instance Property**

The underlying value referenced by the binding variable.

## Declaration

```swift
var wrappedValue: Value { get nonmutating set }
```

## Discussion

This property provides primary access to the value’s data. However, you don’t access `wrappedValue` directly. Instead, you use the property variable created with the [Binding](../Binding.zh-Hans.md) attribute. In the following code example, the binding variable `isPlaying` returns the value of `wrappedValue`:

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

When a mutable binding value changes, the new value is immediately available. However, updates to a view displaying the value happens asynchronously, so the view may not show the change immediately.

## Getting the value

- **projectedValue**: A projection of the binding value that returns a binding.
- **subscript(dynamicMember:)**: Returns a binding to the resulting value of a given key path.

