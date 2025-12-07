---
来源：https://developer.apple.com/documentation/SwiftUI/ButtonToggleStyle/makeBody(配置：)
抓取时间： 2025-12-04T13:11:29Z
---

# makeBody(configuration:)

**实例方法**

创建表示切换按钮主体的视图。

## 声明

```swift
@MainActor @preconcurrency func makeBody(configuration: ButtonToggleStyle.Configuration) -> some View

```

## 参数

- **configuration**：切换开关的属性，包括标签和与切换开关状态的绑定。

## 返回值

一个视图，作为控制布尔状态的按钮。

## 讨论

SwiftUI 实现了[ToggleStyle](../ToggleStyle.zh-Hans.md) 协议的这一必要方法，以定义[button](../ToggleStyle/button.zh-Hans.md) 切换样式的行为和外观。不要直接调用此方法；系统会为视图层次结构中每个样式为按钮的[Toggle](../Toggle.zh-Hans.md) 实例调用此方法。


---
source: https://developer.apple.com/documentation/SwiftUI/ButtonToggleStyle/makeBody(configuration:)
crawled: 2025-12-04T13:11:29Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a toggle button.

## Declaration

```swift
@MainActor @preconcurrency func makeBody(configuration: ButtonToggleStyle.Configuration) -> some View

```

## Parameters

- **configuration**: The properties of the toggle, including a label and a binding to the toggle’s state.

## Return Value

A view that acts as a button that controls a Boolean state.

## Discussion

SwiftUI implements this required method of the [ToggleStyle](../ToggleStyle.zh-Hans.md) protocol to define the behavior and appearance of the [button](../ToggleStyle/button.zh-Hans.md) toggle style. Don’t call this method directly; the system calls this method for each [Toggle](../Toggle.zh-Hans.md) instance in a view hierarchy that’s styled as a button.

