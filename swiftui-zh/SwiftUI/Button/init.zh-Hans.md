--- 来源：https://developer.apple.com/documentation/SwiftUI/Button/init(_:)

抓取时间：2025-12-02T21:48:06Z

---

# init(_:)

**Initializer**

根据自定义样式配置创建一个按钮，该样式具有自定义外观和自定义交互行为。

## 声明

```swift
nonisolated init(_ configuration: PrimitiveButtonStyleConfiguration)
```

## 参数

- **configuration**：自定义样式配置，该样式具有自定义外观和自定义交互行为。

## 说明

在 [PrimitiveButtonStyle](../PrimitiveButtonStyle.zh-Hans.md) 的 [makeBody(configuration:)](../PrimitiveButtonStyle/makeBody_configuration.zh-Hans.md) 方法中使用此初始化器来创建要设置样式的按钮实例。这对于修改当前按钮样式的自定义按钮样式非常有用，而不是实现一个全新的样式。

例如，以下样式会在按钮周围添加红色边框，但保持按钮的现有样式不变：

```swift
struct RedBorderedButtonStyle: PrimitiveButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        Button(configuration)
            .border(Color.red)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/Button/init(_:)
crawled: 2025-12-02T21:48:06Z
---

# init(_:)

**Initializer**

Creates a button based on a configuration for a style with a custom appearance and custom interaction behavior.

## Declaration

```swift
nonisolated init(_ configuration: PrimitiveButtonStyleConfiguration)
```

## Parameters

- **configuration**: A configuration for a style with a custom appearance and custom interaction behavior.

## Discussion

Use this initializer within the [makeBody(configuration:)](../PrimitiveButtonStyle/makeBody_configuration.zh-Hans.md) method of a [PrimitiveButtonStyle](../PrimitiveButtonStyle.zh-Hans.md) to create an instance of the button that you want to style. This is useful for custom button styles that modify the current button style, rather than implementing a brand new style.

For example, the following style adds a red border around the button, but otherwise preserves the button’s current style:

```swift
struct RedBorderedButtonStyle: PrimitiveButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        Button(configuration)
            .border(Color.red)
    }
}
```

