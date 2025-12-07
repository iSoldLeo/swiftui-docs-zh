--- 来源：https://developer.apple.com/documentation/swiftui/togglestyleconfiguration
抓取时间：2025-12-04T13:11:36Z

---

# ToggleStyleConfiguration

**Structure**

切换开关实例的属性。

## 声明

```swift
struct ToggleStyleConfiguration
```

## 概述

当您通过创建符合 [ToggleStyle](ToggleStyle.zh-Hans.md) 协议的类型来定义自定义切换开关样式时，您需要实现 [makeBody(configuration:)](ToggleStyle/makeBody_configuration.zh-Hans.md) 方法。该方法接受一个 `ToggleStyleConfiguration` 输入，其中包含定义 [Toggle](Toggle.zh-Hans.md) 开关的行为和外观所需的信息。

配置结构中的 [label-swift.property](ToggleStyleConfiguration/label-swift_property.zh-Hans.md) 反映了切换开关的内容，这可能是您提供给 [init(isOn:label:)](Toggle/init_isOn_label.zh-Hans.md) 初始化器 `label` 参数的值。或者，它也可能是 SwiftUI 根据接受字符串输入的初始化器构建的另一个视图，例如 [init(_:isOn:)](Toggle/init___isOn.zh-Hans.md)。无论哪种情况，都应将标签集成到切换开关的视图中，以帮助用户理解切换开关的功能。例如，内置的 [switch](ToggleStyle/switch.zh-Hans.md) 样式会将标签与控件元素水平堆叠。

该结构的 [isOn](ToggleStyleConfiguration/isOn.zh-Hans.md) 属性为切换开关的状态提供 [Binding](Binding.zh-Hans.md)。根据此值调整切换开关的外观。例如，内置样式 [button](ToggleStyle/button.zh-Hans.md) 在属性值为 `true` 时填充按钮背景，而当属性值为 `false` 时则保持背景为空。当用户执行旨在更改切换状态的操作（例如用户点击或单击按钮）时，更改该值。

## 获取标签视图

- **label**：描述切换状态效果的视图。

- **ToggleStyleConfiguration.Label**：切换状态的已擦除文本的标签。

## 管理切换状态

- **isMixed**：[Toggle](Toggle.zh-Hans.md) 当前是否处于混合状态。

- **isOn**：绑定到状态属性，指示切换开关是否开启。

- **$isOn**

## 切换开关样式

- **toggleStyle(_:)**：设置视图层级结构中切换开关的样式。

- **ToggleStyle**：切换开关的外观和行为。


---
source: https://developer.apple.com/documentation/swiftui/togglestyleconfiguration
crawled: 2025-12-04T13:11:36Z
---

# ToggleStyleConfiguration

**Structure**

The properties of a toggle instance.

## Declaration

```swift
struct ToggleStyleConfiguration
```

## Overview

When you define a custom toggle style by creating a type that conforms to the [ToggleStyle](ToggleStyle.zh-Hans.md) protocol, you implement the [makeBody(configuration:)](ToggleStyle/makeBody_configuration.zh-Hans.md) method. That method takes a `ToggleStyleConfiguration` input that has the information you need to define the behavior and appearance of a [Toggle](Toggle.zh-Hans.md).

The configuration structure’s [label-swift.property](ToggleStyleConfiguration/label-swift_property.zh-Hans.md) reflects the toggle’s content, which might be the value that you supply to the `label` parameter of the [init(isOn:label:)](Toggle/init_isOn_label.zh-Hans.md) initializer. Alternatively, it could be another view that SwiftUI builds from an initializer that takes a string input, like [init(_:isOn:)](Toggle/init___isOn.zh-Hans.md). In either case, incorporate the label into the toggle’s view to help the user understand what the toggle does. For example, the built-in [switch](ToggleStyle/switch.zh-Hans.md) style horizontally stacks the label with the control element.

The structure’s [isOn](ToggleStyleConfiguration/isOn.zh-Hans.md) property provides a [Binding](Binding.zh-Hans.md) to the state of the toggle. Adjust the appearance of the toggle based on this value. For example, the built-in [button](ToggleStyle/button.zh-Hans.md) style fills the button’s background when the property is `true`, but leaves the background empty when the property is `false`. Change the value when the user performs an action that’s meant to change the toggle, like the button does when tapped or clicked by the user.

## Getting the label view

- **label**: A view that describes the effect of switching the toggle between states.
- **ToggleStyleConfiguration.Label**: A type-erased label of a toggle.

## Managing the toggle state

- **isMixed**: Whether the [Toggle](Toggle.zh-Hans.md) is currently in a mixed state.
- **isOn**: A binding to a state property that indicates whether the toggle is on.
- **$isOn**

## Styling toggles

- **toggleStyle(_:)**: Sets the style for toggles in a view hierarchy.
- **ToggleStyle**: The appearance and behavior of a toggle.

