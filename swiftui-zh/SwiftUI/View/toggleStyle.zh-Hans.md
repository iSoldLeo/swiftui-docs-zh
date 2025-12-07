--- 来源：https://developer.apple.com/documentation/SwiftUI/View/toggleStyle(_:)

抓取时间：2025-11-30T21:18:19Z

---

# toggleStyle(_:)

**实例方法**

设置视图层级结构中切换按钮的样式。

## 声明

```swift
nonisolated func toggleStyle<S>(_ style: S) -> some View where S : ToggleStyle

```

## 参数

- **style**：要设置的切换按钮样式。可以使用内置值，例如 [switch](../ToggleStyle/switch.zh-Hans.md) 或 [button](../ToggleStyle/button.zh-Hans.md)，也可以使用自定义样式，该自定义样式是通过创建符合 [ToggleStyle](../ToggleStyle.zh-Hans.md) 协议的类型来定义的。

## 返回值

一个视图，该视图及其子视图都使用指定的切换按钮样式。

## 讨论

在 [Toggle](../Toggle.zh-Hans.md) 实例上使用此修饰符，可以设置定义控件外观和行为的样式。例如，您可以选择 [switch](../ToggleStyle/switch.zh-Hans.md) 样式：

```swift
Toggle("Vibrate on Ring", isOn: $vibrateOnRing)
    .toggleStyle(.switch)
```

内置样式通常在不同平台上具有相似的外观，并根据平台的整体风格进行调整：

### 为层级结构中的切换开关设置样式

您可以通过将样式修饰符应用于容器视图，为视图层级结构中的所有切换开关实例设置样式。例如，您可以将样式 [button](../ToggleStyle/button.zh-Hans.md) 应用于 [HStack](../HStack.zh-Hans.md)：

```swift
HStack {
    Toggle(isOn: $isFlagged) {
        Label("Flag", systemImage: "flag.fill")
    }
    Toggle(isOn: $isMuted) {
        Label("Mute", systemImage: "speaker.slash.fill")
    }
}
.toggleStyle(.button)
```

当 `isFlagged` 为 `true` 且 `isMuted` 为 `false` 时，上述示例的外观如下：

### 自动样式

如果您未设置样式，SwiftUI 会假定值为 [automatic](../ToggleStyle/automatic.zh-Hans.md)，这对应于特定于上下文的默认值。显式指定自动样式可以覆盖容器的样式并恢复为默认值：

```swift
HStack {
    Toggle(isOn: $isShuffling) {
        Label("Shuffle", systemImage: "shuffle")
    }
    Toggle(isOn: $isRepeating) {
        Label("Repeat", systemImage: "repeat")
    }

    Divider()

    Toggle("Enhance Sound", isOn: $isEnhanced)
        .toggleStyle(.automatic) // Revert to the default style.
}
.toggleStyle(.button) // Use button style for toggles in the stack.
.labelStyle(.iconOnly) // Omit the title from any labels.
```

SwiftUI 用作默认样式的样式取决于平台和上下文。在 macOS 中，大多数情况下默认样式为 [checkbox](../ToggleStyle/checkbox.zh-Hans.md)，而在 iOS 中，默认切换样式为 [switch](../ToggleStyle/switch.zh-Hans.md)：

有关 SwiftUI 如何选择默认切换样式的更多信息，请参阅 [automatic](../ToggleStyle/automatic.zh-Hans.md) 样式。

## 获取数值输入

- **Slider**：用于从有界线性值范围内选择值的控件。

- **Stepper**：用于执行递增和递减操作的控件。

- **Toggle**：用于在开启和关闭状态之间切换的控件。


---
source: https://developer.apple.com/documentation/SwiftUI/View/toggleStyle(_:)
crawled: 2025-11-30T21:18:19Z
---

# toggleStyle(_:)

**Instance Method**

Sets the style for toggles in a view hierarchy.

## Declaration

```swift
nonisolated func toggleStyle<S>(_ style: S) -> some View where S : ToggleStyle

```

## Parameters

- **style**: The toggle style to set. Use one of the built-in values, like [switch](../ToggleStyle/switch.zh-Hans.md) or [button](../ToggleStyle/button.zh-Hans.md), or a custom style that you define by creating a type that conforms to the [ToggleStyle](../ToggleStyle.zh-Hans.md) protocol.

## Return Value

A view that uses the specified toggle style for itself and its child views.

## Discussion

Use this modifier on a [Toggle](../Toggle.zh-Hans.md) instance to set a style that defines the control’s appearance and behavior. For example, you can choose the [switch](../ToggleStyle/switch.zh-Hans.md) style:

```swift
Toggle("Vibrate on Ring", isOn: $vibrateOnRing)
    .toggleStyle(.switch)
```

Built-in styles typically have a similar appearance across platforms, tailored to the platform’s overall style:



### Styling toggles in a hierarchy

You can set a style for all toggle instances within a view hierarchy by applying the style modifier to a container view. For example, you can apply the [button](../ToggleStyle/button.zh-Hans.md) style to an [HStack](../HStack.zh-Hans.md):

```swift
HStack {
    Toggle(isOn: $isFlagged) {
        Label("Flag", systemImage: "flag.fill")
    }
    Toggle(isOn: $isMuted) {
        Label("Mute", systemImage: "speaker.slash.fill")
    }
}
.toggleStyle(.button)
```

The example above has the following appearance when `isFlagged` is `true` and `isMuted` is `false`:



### Automatic styling

If you don’t set a style, SwiftUI assumes a value of [automatic](../ToggleStyle/automatic.zh-Hans.md), which corresponds to a context-specific default. Specify the automatic style explicitly to override a container’s style and revert to the default:

```swift
HStack {
    Toggle(isOn: $isShuffling) {
        Label("Shuffle", systemImage: "shuffle")
    }
    Toggle(isOn: $isRepeating) {
        Label("Repeat", systemImage: "repeat")
    }

    Divider()

    Toggle("Enhance Sound", isOn: $isEnhanced)
        .toggleStyle(.automatic) // Revert to the default style.
}
.toggleStyle(.button) // Use button style for toggles in the stack.
.labelStyle(.iconOnly) // Omit the title from any labels.
```

The style that SwiftUI uses as the default depends on both the platform and the context. In macOS, the default in most contexts is a [checkbox](../ToggleStyle/checkbox.zh-Hans.md), while in iOS, the default toggle style is a [switch](../ToggleStyle/switch.zh-Hans.md):





For more information about how SwiftUI chooses a default toggle style, see the [automatic](../ToggleStyle/automatic.zh-Hans.md) style.

## Getting numeric inputs

- **Slider**: A control for selecting a value from a bounded linear range of values.
- **Stepper**: A control that performs increment and decrement actions.
- **Toggle**: A control that toggles between on and off states.

