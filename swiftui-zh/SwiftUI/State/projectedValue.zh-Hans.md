---
来源： https://developer.apple.com/documentation/SwiftUI/State/projectedValue
抓取时间： 2025-12-03T06:06:33Z
---

# 预计值

**实例属性**

状态值的绑定。

## 声明

```swift
var projectedValue: Binding<Value> { get }
```

## 讨论

使用预测值可获得与存储值的[Binding](../Binding.zh-Hans.md)绑定。绑定提供了与存储值的双向连接。要访问`projectedValue`，请在属性变量前加上美元符号 (`$`)。

在下面的示例中，`PlayerView` 使用 `$isPlaying` 将状态属性 `isPlaying` 绑定到 `PlayButton` 视图。这样，播放按钮就可以同时读取和写入数值：

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

- **wrappedValue**：状态变量引用的基础值。


---
source: https://developer.apple.com/documentation/SwiftUI/State/projectedValue
crawled: 2025-12-03T06:06:33Z
---

# projectedValue

**Instance Property**

A binding to the state value.

## Declaration

```swift
var projectedValue: Binding<Value> { get }
```

## Discussion

Use the projected value to get a [Binding](../Binding.zh-Hans.md) to the stored value. The binding provides a two-way connection to the stored value. To access the `projectedValue`, prefix the property variable with a dollar sign (`$`).

In the following example, `PlayerView` projects a binding of the state property `isPlaying` to the `PlayButton` view using `$isPlaying`. That enables the play button to both read and write the value:

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

- **wrappedValue**: The underlying value referenced by the state variable.

