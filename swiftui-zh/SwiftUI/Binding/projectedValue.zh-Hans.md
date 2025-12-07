---
来源： https://developer.apple.com/documentation/SwiftUI/Binding/projectedValue
抓取时间：2025-12-03T06:06:41Z
---

# 预计值

**实例属性**

绑定值的投影，返回一个绑定。

## 声明

```swift
var projectedValue: Binding<Value> { get }
```

## 讨论

使用预测值可将绑定值向下传递到视图层次。要获取`projectedValue`，请在属性变量前加上`$`。例如，在下面的代码示例中，`PlayerView` 使用 `$isPlaying` 将状态属性 `isPlaying` 绑定到 `PlayButton` 视图。

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var isPlaying: Bool = false

    var body: some View {
        VStack {
            Text(episode.title)
                .foregroundStyle(isPlaying ? .primary : .secondary)
            PlayButton(isPlaying: $isPlaying)
        }
    }
}
```

## 获取值

- **wrappedValue**：绑定变量引用的基础值。
- **subscript(dynamicMember:)**：返回绑定到给定键路径的结果值。


---
source: https://developer.apple.com/documentation/SwiftUI/Binding/projectedValue
crawled: 2025-12-03T06:06:41Z
---

# projectedValue

**Instance Property**

A projection of the binding value that returns a binding.

## Declaration

```swift
var projectedValue: Binding<Value> { get }
```

## Discussion

Use the projected value to pass a binding value down a view hierarchy. To get the `projectedValue`, prefix the property variable with `$`. For example, in the following code example `PlayerView` projects a binding of the state property `isPlaying` to the `PlayButton` view using `$isPlaying`.

```swift
struct PlayerView: View {
    var episode: Episode
    @State private var isPlaying: Bool = false

    var body: some View {
        VStack {
            Text(episode.title)
                .foregroundStyle(isPlaying ? .primary : .secondary)
            PlayButton(isPlaying: $isPlaying)
        }
    }
}
```

## Getting the value

- **wrappedValue**: The underlying value referenced by the binding variable.
- **subscript(dynamicMember:)**: Returns a binding to the resulting value of a given key path.

