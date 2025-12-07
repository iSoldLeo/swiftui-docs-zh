---
来源：https://developer.apple.com/documentation/SwiftUI/ToggleStyle/makeBody(配置：)
抓取时间： 2025-12-03T06:09:49Z
---

# makeBody(configuration:)

**实例方法**

创建表示切换主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：切换开关的属性，包括标签和与切换开关状态的绑定。

## 返回值

一个视图，它的行为和外观使其能够作为 [Toggle](../Toggle.zh-Hans.md).SY_0022⟧"视图 "使用。

## 讨论

当您定义符合[ToggleStyle](../ToggleStyle.zh-Hans.md) 协议的自定义切换样式时，请执行此方法。使用 `configuration` 输入--一个 [ToggleStyleConfiguration](../ToggleStyleConfiguration.zh-Hans.md) 实例--访问切换按钮的标签和状态。返回具有切换视图外观和行为的视图。例如，您可以创建一个切换视图，显示一个标签和一个圆圈，该圆圈可以是空的，也可以填上复选标记：

```swift
struct ChecklistToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Button {
            configuration.isOn.toggle()
        } label: {
            HStack {
                Image(systemName: configuration.isOn
                        ? "checkmark.circle.fill"
                        : "circle")
                configuration.label
            }
        }
        .tint(.primary)
        .buttonStyle(.borderless)
    }
}
```

`ChecklistToggleStyle`切换样式提供了一种观察和修改切换状态的方法：圆圈填充表示打开状态，用户可以点击或单击切换按钮来改变状态。通过使用自定义的[Button](../Button.zh-Hans.md) 来组成切换体，SwiftUI 可以自动提供用户期望从具有按钮特性的控件中获得的行为。

您可以在堆栈中展示使用这种样式的切换按钮集合：



更新视图层次结构时，系统会为每个使用相关样式的 [Toggle](../Toggle.zh-Hans.md) 实例调用您的 `makeBody(configuration:)` 方法的实现。

### 修改当前样式

与其创建一个全新的样式，还不如修改切换开关的当前样式。使用`makeBody(configuration:)` 方法中的[init(_:)](../Toggle/init.zh-Hans.md) 初始化器，根据`configuration` 值创建和修改切换样式。例如，您可以创建一个样式，为当前样式添加填充和红色边框：

```swift
struct RedBorderToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Toggle(configuration)
            .padding()
            .border(.red)
    }
}
```

如果从该样式创建一个 `redBorder` 静态变量，就可以将该样式应用到已经使用另一种样式的切换器上，如内置的 [switch](switch.zh-Hans.md) 和 [button](button.zh-Hans.md) 样式：

```swift
Toggle("Switch", isOn: $isSwitchOn)
    .toggleStyle(.redBorder)
    .toggleStyle(.switch)

Toggle("Button", isOn: $isButtonOn)
    .toggleStyle(.redBorder)
    .toggleStyle(.button)
```

这两个切换按钮都以常规样式出现，每个都有红色边框：



应用自定义样式比修改样式更靠近切换按钮，因为 SwiftUI 评估样式视图修改器的顺序是从最外层到最内层。如果按其他顺序应用样式，红色边框样式将不起作用，因为内置样式会完全覆盖它。

## 创建自定义切换样式

- **ToggleStyleConfiguration**：切换实例的属性。
- **ToggleStyle.Configuration**：切换实例的属性。
- **Body**：表示切换开关的外观和交互的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ToggleStyle/makeBody(configuration:)
crawled: 2025-12-03T06:09:49Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a toggle.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the toggle, including a label and a binding to the toggle’s state.

## Return Value

A view that has behavior and appearance that enables it to function as a [Toggle](../Toggle.zh-Hans.md).

## Discussion

Implement this method when you define a custom toggle style that conforms to the [ToggleStyle](../ToggleStyle.zh-Hans.md) protocol. Use the `configuration` input — a [ToggleStyleConfiguration](../ToggleStyleConfiguration.zh-Hans.md) instance — to access the toggle’s label and state. Return a view that has the appearance and behavior of a toggle. For example you can create a toggle that displays a label and a circle that’s either empty or filled with a checkmark:

```swift
struct ChecklistToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Button {
            configuration.isOn.toggle()
        } label: {
            HStack {
                Image(systemName: configuration.isOn
                        ? "checkmark.circle.fill"
                        : "circle")
                configuration.label
            }
        }
        .tint(.primary)
        .buttonStyle(.borderless)
    }
}
```

The `ChecklistToggleStyle` toggle style provides a way to both observe and modify the toggle state: the circle fills for the on state, and users can tap or click the toggle to change the state. By using a customized [Button](../Button.zh-Hans.md) to compose the toggle’s body, SwiftUI automatically provides the behaviors that users expect from a control that has button-like characteristics.

You can present a collection of toggles that use this style in a stack:



When updating a view hierarchy, the system calls your implementation of the `makeBody(configuration:)` method for each [Toggle](../Toggle.zh-Hans.md) instance that uses the associated style.

### Modify the current style

Rather than create an entirely new style, you can alternatively modify a toggle’s current style. Use the [init(_:)](../Toggle/init.zh-Hans.md) initializer inside the `makeBody(configuration:)` method to create and modify a toggle based on a `configuration` value. For example, you can create a style that adds padding and a red border to the current style:

```swift
struct RedBorderToggleStyle: ToggleStyle {
    func makeBody(configuration: Configuration) -> some View {
        Toggle(configuration)
            .padding()
            .border(.red)
    }
}
```

If you create a `redBorder` static variable from this style, you can apply the style to toggles that already use another style, like the built-in [switch](switch.zh-Hans.md) and [button](button.zh-Hans.md) styles:

```swift
Toggle("Switch", isOn: $isSwitchOn)
    .toggleStyle(.redBorder)
    .toggleStyle(.switch)

Toggle("Button", isOn: $isButtonOn)
    .toggleStyle(.redBorder)
    .toggleStyle(.button)
```

Both toggles appear with the usual styling, each with a red border:



Apply the custom style closer to the toggle than the modified style because SwiftUI evaluates style view modifiers in order from outermost to innermost. If you apply the styles in the other order, the red border style doesn’t have an effect, because the built-in styles override it completely.

## Creating custom toggle styles

- **ToggleStyleConfiguration**: The properties of a toggle instance.
- **ToggleStyle.Configuration**: The properties of a toggle instance.
- **Body**: A view that represents the appearance and interaction of a toggle.

