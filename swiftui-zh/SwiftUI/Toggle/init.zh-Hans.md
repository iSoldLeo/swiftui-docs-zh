---
来源： https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:)
抓取时间： 2025-12-01T02:45:33Z
---

# init(_:)

**Initializer**

根据切换样式配置创建一个切换器。

## 声明

```swift
nonisolated init(_ configuration: ToggleStyleConfiguration)
```

## 参数

- **configuration**：切换开关的属性，包括标签和与切换开关状态的绑定。

## 讨论

您可以在[makeBody(configuration:)](../ToggleStyle/makeBody_configuration.zh-Hans.md) 方法中使用该初始化器来创建一个样式化的切换实例。这对于只修改当前切换样式的自定义切换样式非常有用，而不是实现一个全新的样式。

例如，以下样式在切换框周围添加了红色边框，但保留了切换框的当前样式：

```swift
struct RedBorderToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Toggle(configuration)
            .padding()
            .border(.red)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Toggle/init(_:)
crawled: 2025-12-01T02:45:33Z
---

# init(_:)

**Initializer**

Creates a toggle based on a toggle style configuration.

## Declaration

```swift
nonisolated init(_ configuration: ToggleStyleConfiguration)
```

## Parameters

- **configuration**: The properties of the toggle, including a label and a binding to the toggle’s state.

## Discussion

You can use this initializer within the [makeBody(configuration:)](../ToggleStyle/makeBody_configuration.zh-Hans.md) method of a [ToggleStyle](../ToggleStyle.zh-Hans.md) to create an instance of the styled toggle. This is useful for custom toggle styles that only modify the current toggle style, as opposed to implementing a brand new style.

For example, the following style adds a red border around the toggle, but otherwise preserves the toggle’s current style:

```swift
struct RedBorderToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Toggle(configuration)
            .padding()
            .border(.red)
    }
}
```

