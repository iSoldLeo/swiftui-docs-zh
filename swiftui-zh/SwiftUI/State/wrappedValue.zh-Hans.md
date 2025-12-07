---
来源： https://developer.apple.com/documentation/SwiftUI/State/wrappedValue
抓取时间： 2025-12-03T06:06:32Z
---

# wrappedValue

**实例属性**

状态变量引用的基础值。

## 声明

```swift
var wrappedValue: Value { get nonmutating set }
```

## 讨论

该属性提供了对值数据的主要访问权限。但是，您通常不会明确访问 `wrappedValue`。取而代之的是，通过引用使用`@State` 属性创建的属性变量来访问封装值。

在下面的示例中，按钮的标签取决于`isPlaying` 的值，而按钮的操作会切换`isPlaying` 的值。这两种访问方式都隐式地访问了状态属性的包装值：

```swift
struct PlayButton: View {
    @State private var isPlaying: Bool = false

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") {
            isPlaying.toggle()
        }
    }
}
```

## 获取值

- **projectedValue**：与状态值绑定。


---
source: https://developer.apple.com/documentation/SwiftUI/State/wrappedValue
crawled: 2025-12-03T06:06:32Z
---

# wrappedValue

**Instance Property**

The underlying value referenced by the state variable.

## Declaration

```swift
var wrappedValue: Value { get nonmutating set }
```

## Discussion

This property provides primary access to the value’s data. However, you don’t typically access `wrappedValue` explicitly. Instead, you gain access to the wrapped value by referring to the property variable that you create with the `@State` attribute.

In the following example, the button’s label depends on the value of `isPlaying` and the button’s action toggles the value of `isPlaying`. Both of these accesses implicitly access the state property’s wrapped value:

```swift
struct PlayButton: View {
    @State private var isPlaying: Bool = false

    var body: some View {
        Button(isPlaying ? "Pause" : "Play") {
            isPlaying.toggle()
        }
    }
}
```

## Getting the value

- **projectedValue**: A binding to the state value.

