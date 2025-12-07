--- 来源：https://developer.apple.com/documentation/swiftui/toggle

抓取时间：2025-12-04T13:11:37Z

---

# 切换

**Structure**

用于在开启和关闭状态之间切换的控件。

## 声明

```swift
struct Toggle<Label> where Label : View
```

## 概述

您可以通过提供 `isOn` 绑定和标签来创建切换控件。将 `isOn` 绑定到一个布尔属性，该属性决定切换控件是开启还是关闭。将标签设置为一个视图，该视图以可视化的方式描述切换状态的目的。例如：

```swift
@State private var vibrateOnRing = false

var body: some View {
    Toggle(isOn: $vibrateOnRing) {
        Text("Vibrate on Ring")
    }
}
```

对于常见的基于 [Label](Label.zh-Hans.md) 的标签，您可以使用便捷初始化器，它接受一个标题字符串（或本地化字符串键）和一个系统映像名称：

```swift
@State private var vibrateOnRing = true

var body: some View {
    Toggle(
        "Vibrate on Ring",
        systemImage: "dot.radiowaves.left.and.right",
        isOn: $vibrateOnRing
    )
}
```

对于纯文本标签，您可以使用便捷初始化器，它接受一个标题字符串（或本地化字符串键）作为其第一个参数，而不是尾随闭包：

```swift
@State private var vibrateOnRing = true

var body: some View {
    Toggle("Vibrate on Ring", isOn: $vibrateOnRing)
}
```

如果需要为标签添加副标题，请使用视图构建器创建多个 `Text` 视图，其中第一个文本表示标题，第二个文本表示副标题：

```swift
@State private var vibrateOnRing = false

var body: some View {
    Toggle(isOn: $vibrateOnRing) {
        Text("Vibrate on Ring")
        Text("Enable vibration when the phone rings")
    }
}
```

### 样式切换

切换器使用默认样式，该样式会根据平台和上下文而变化。更多信息，请参阅 [automatic](ToggleStyle/automatic.zh-Hans.md) 切换样式。

您可以使用 [toggleStyle(_:)](View/toggleStyle.zh-Hans.md) 修饰符应用样式来自定义切换按钮的外观和交互方式。您可以将内置样式（例如 [switch](ToggleStyle/switch.zh-Hans.md)）应用于切换按钮，或应用于包含切换按钮的视图层级结构：

```swift
VStack {
    Toggle("Vibrate on Ring", isOn: $vibrateOnRing)
    Toggle("Vibrate on Silent", isOn: $vibrateOnSilent)
}
.toggleStyle(.switch)
```

您还可以通过创建符合 [ToggleStyle](ToggleStyle.zh-Hans.md) 协议的类型来定义自定义样式。

## 创建切换按钮

- **init(_:isOn:)**：创建一个切换按钮，其标签由本地化字符串键生成。

- **init(isOn:label:)**：创建一个显示自定义标签的切换按钮。

- **init(_:image:isOn:)**：创建一个切换开关，其标签由本地化字符串键和图像资源生成。

- **init(_:systemImage:isOn:)**：创建一个切换开关，其标签由本地化字符串键和系统图像生成。

## 为集合创建切换开关

- **init(_:sources:isOn:)**：创建一个表示值集合的切换开关，其标签由本地化字符串键生成。

- **init(sources:isOn:label:)**：创建一个表示具有自定义标签的值集合的切换开关。

- **init(_:image:sources:isOn:)**：创建一个表示值集合的切换开关，其标签由本地化字符串键和图像资源生成。

- **init(_:systemImage:sources:isOn:)**：创建一个表示值集合的切换开关，其标签由本地化字符串键和系统图像生成。

## 根据配置创建切换开关

- **init(_:)**：根据切换开关样式配置创建切换开关。

## 为应用意图创建切换开关

- **init(isOn:intent:label:)**：创建执行 `AppIntent` 的切换开关。

- **init(_:isOn:intent:)**：创建执行 `AppIntent` 的切换开关，并根据本地化字符串键生成其标签。

## 获取数值输入

- **Slider**：用于从有界线性值范围内选择值的控件。

- **Stepper**：用于执行递增和递减操作的控件。

- **toggleStyle(_:)**：设置视图层次结构中切换开关的样式。

## 符合

- 查看


---
source: https://developer.apple.com/documentation/swiftui/toggle
crawled: 2025-12-04T13:11:37Z
---

# Toggle

**Structure**

A control that toggles between on and off states.

## Declaration

```swift
struct Toggle<Label> where Label : View
```

## Overview

You create a toggle by providing an `isOn` binding and a label. Bind `isOn` to a Boolean property that determines whether the toggle is on or off. Set the label to a view that visually describes the purpose of switching between toggle states. For example:

```swift
@State private var vibrateOnRing = false

var body: some View {
    Toggle(isOn: $vibrateOnRing) {
        Text("Vibrate on Ring")
    }
}
```

For the common case of [Label](Label.zh-Hans.md) based labels, you can use the convenience initializer that takes a title string (or localized string key) and the name of a system image:

```swift
@State private var vibrateOnRing = true

var body: some View {
    Toggle(
        "Vibrate on Ring",
        systemImage: "dot.radiowaves.left.and.right",
        isOn: $vibrateOnRing
    )
}
```

For text-only labels, you can use the convenience initializer that takes a title string (or localized string key) as its first parameter, instead of a trailing closure:

```swift
@State private var vibrateOnRing = true

var body: some View {
    Toggle("Vibrate on Ring", isOn: $vibrateOnRing)
}
```

For cases where adding a subtitle to the label is desired, use a view builder that creates multiple `Text` views where the first text represents the title and the second text represents the subtitle:

```swift
@State private var vibrateOnRing = false

var body: some View {
    Toggle(isOn: $vibrateOnRing) {
        Text("Vibrate on Ring")
        Text("Enable vibration when the phone rings")
    }
}
```



### Styling toggles

Toggles use a default style that varies based on both the platform and the context. For more information, read about the [automatic](ToggleStyle/automatic.zh-Hans.md) toggle style.

You can customize the appearance and interaction of toggles by applying styles using the [toggleStyle(_:)](View/toggleStyle.zh-Hans.md) modifier. You can apply built-in styles, like [switch](ToggleStyle/switch.zh-Hans.md), to either a toggle, or to a view hierarchy that contains toggles:

```swift
VStack {
    Toggle("Vibrate on Ring", isOn: $vibrateOnRing)
    Toggle("Vibrate on Silent", isOn: $vibrateOnSilent)
}
.toggleStyle(.switch)
```

You can also define custom styles by creating a type that conforms to the [ToggleStyle](ToggleStyle.zh-Hans.md) protocol.

## Creating a toggle

- **init(_:isOn:)**: Creates a toggle that generates its label from a localized string key.
- **init(isOn:label:)**: Creates a toggle that displays a custom label.
- **init(_:image:isOn:)**: Creates a toggle that generates its label from a localized string key and image resource.
- **init(_:systemImage:isOn:)**: Creates a toggle that generates its label from a localized string key and system image.

## Creating a toggle for a collection

- **init(_:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key.
- **init(sources:isOn:label:)**: Creates a toggle representing a collection of values with a custom label.
- **init(_:image:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key and image resource.
- **init(_:systemImage:sources:isOn:)**: Creates a toggle representing a collection of values that generates its label from a localized string key and system image.

## Creating a toggle from a configuration

- **init(_:)**: Creates a toggle based on a toggle style configuration.

## Creating a toggle for an App Intent

- **init(isOn:intent:label:)**: Creates a toggle performing an `AppIntent`.
- **init(_:isOn:intent:)**: Creates a toggle performing an `AppIntent` and generates its label from a localized string key.

## Getting numeric inputs

- **Slider**: A control for selecting a value from a bounded linear range of values.
- **Stepper**: A control that performs increment and decrement actions.
- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.

## Conforms To

- View

