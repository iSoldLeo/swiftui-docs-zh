---
来源： https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:)
抓取时间： 2025-12-01T10:29:41Z
---

# init(_:)

**Initializer**

根据样式配置创建控制组。

## 声明

```swift
nonisolated init(_ configuration: ControlGroupStyleConfiguration)
```

## 讨论

在[makeBody(configuration:)](../ControlGroupStyle/makeBody_configuration.zh-Hans.md) 实例的[ControlGroupStyle](../ControlGroupStyle.zh-Hans.md) 方法中使用此初始化器，可创建一个被样式化的控件组实例。这对于修改当前控件组样式的自定义控件组样式非常有用。

例如，以下代码会创建一个新的自定义样式，在当前控件组周围添加红色边框：

```swift
struct RedBorderControlGroupStyle: ControlGroupStyle {
    func makeBody(configuration: Configuration) -> some View {
        ControlGroup(configuration)
            .border(Color.red)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroup/init(_:)
crawled: 2025-12-01T10:29:41Z
---

# init(_:)

**Initializer**

Creates a control group based on a style configuration.

## Declaration

```swift
nonisolated init(_ configuration: ControlGroupStyleConfiguration)
```

## Discussion

Use this initializer within the [makeBody(configuration:)](../ControlGroupStyle/makeBody_configuration.zh-Hans.md) method of a [ControlGroupStyle](../ControlGroupStyle.zh-Hans.md) instance to create an instance of the control group being styled. This is useful for custom control group styles that modify the current control group style.

For example, the following code creates a new, custom style that places a red border around the current control group:

```swift
struct RedBorderControlGroupStyle: ControlGroupStyle {
    func makeBody(configuration: Configuration) -> some View {
        ControlGroup(configuration)
            .border(Color.red)
    }
}
```

