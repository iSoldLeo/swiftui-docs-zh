--- 来源：https://developer.apple.com/documentation/SwiftUI/View/buttonSizing(_:)

抓取时间：2025-12-02T17:22:37Z

---

# buttonSizing(_:)

**实例方法**

视图层级结构中按钮的首选尺寸调整行为。

## 声明

```swift
nonisolated func buttonSizing(_ sizing: ButtonSizing) -> some View

```

## 参数

- **sizing**：按钮尺寸调整行为，可用于影响能够适应此行为的按钮的主轴尺寸。

## 说明

视图在确定其主轴尺寸（在其父视图建议尺寸范围内）时，可以使用指定的按钮尺寸调整行为。

许多显示为按钮的内置控件都会适应此视图修饰符。例如，您可以将此修饰符应用于 [Button](../Button.zh-Hans.md)、[Picker](../Picker.zh-Hans.md)、[ControlGroup](../ControlGroup.zh-Hans.md) 和 [Toggle](../Toggle.zh-Hans.md) 的某些样式或其容器，从而使其具有弹性。

此示例创建了一个横跨其容器宽度的按钮，如果按钮放置在较窄的上下文中（例如欢迎窗口的侧边栏），则可能需要这样做。

```swift
Button("Open Document…", action: openDocument)
    .buttonSizing(.flexible)
```

您可以通过读取 [buttonSizing](../EnvironmentValues/buttonSizing.zh-Hans.md) 环境值并应用适当的框架，使您自己的视图和样式适应此视图修饰符。

```swift
struct CustomButtonStyle: ButtonStyle {
    @Environment(\.buttonSizing) private var buttonSizing

    private var maxWidth: CGFloat {
        switch buttonSizing {
        case .flexible: .infinity
        case .fitted, _: nil
        }
    }

    func makeBody(configuration: Configuration) -> some View {
        configuration.content
            .frame(maxWidth: maxWidth)
            .background(.tint, in: Capsule())
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/buttonSizing(_:)
crawled: 2025-12-02T17:22:37Z
---

# buttonSizing(_:)

**Instance Method**

The preferred sizing behavior of buttons in the view hierarchy.

## Declaration

```swift
nonisolated func buttonSizing(_ sizing: ButtonSizing) -> some View

```

## Parameters

- **sizing**: A button sizing behavior that may be used to influence the primary axis size of buttons capable of adapting to it.

## Discussion

Views may use the specified button sizing when determining the size they choose to be in their primary axis within their parent view’s proposed size.

Many built-in controls that display as a button adapt to this view modifier. For example, you can make certain styles of [Button](../Button.zh-Hans.md), [Picker](../Picker.zh-Hans.md), [ControlGroup](../ControlGroup.zh-Hans.md), and [Toggle](../Toggle.zh-Hans.md) flexible by applying this modifier to them or their container.

This example creates a button that spans the width of its container, which you may want to do if the button is placed in a narrow context, like the sidebar of a welcome window.

```swift
Button("Open Document…", action: openDocument)
    .buttonSizing(.flexible)
```

Your own views and styles can adapt to this view modifier by reading the [buttonSizing](../EnvironmentValues/buttonSizing.zh-Hans.md) environment value and applying an appropriate frame.

```swift
struct CustomButtonStyle: ButtonStyle {
    @Environment(\.buttonSizing) private var buttonSizing

    private var maxWidth: CGFloat {
        switch buttonSizing {
        case .flexible: .infinity
        case .fitted, _: nil
        }
    }

    func makeBody(configuration: Configuration) -> some View {
        configuration.content
            .frame(maxWidth: maxWidth)
            .background(.tint, in: Capsule())
    }
}
```

