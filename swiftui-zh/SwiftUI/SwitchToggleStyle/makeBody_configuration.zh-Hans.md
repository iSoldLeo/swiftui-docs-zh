--- 来源：https://developer.apple.com/documentation/SwiftUI/SwitchToggleStyle/makeBody(configuration:)

抓取时间：2025-12-04T13:11:34Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示切换开关主体的视图。

## 声明

```swift
@MainActor @preconcurrency func makeBody(configuration: SwitchToggleStyle.Configuration) -> some View

```

## 参数

- **configuration**：切换开关的属性，包括标签和与切换开关状态的绑定。

## 返回值

一个表示切换开关的视图。

## 说明

SwiftUI 实现了 [ToggleStyle](../ToggleStyle.zh-Hans.md) 协议的此必需方法，以定义 [switch](../ToggleStyle/switch.zh-Hans.md) 切换开关样式的行为和外观。不要直接调用此方法。系统会针对视图层级结构中每个样式为开关的 [Toggle](../Toggle.zh-Hans.md) 实例调用此方法。


---
source: https://developer.apple.com/documentation/SwiftUI/SwitchToggleStyle/makeBody(configuration:)
crawled: 2025-12-04T13:11:34Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a toggle switch.

## Declaration

```swift
@MainActor @preconcurrency func makeBody(configuration: SwitchToggleStyle.Configuration) -> some View

```

## Parameters

- **configuration**: The properties of the toggle, including a label and a binding to the toggle’s state.

## Return Value

A view that represents a switch.

## Discussion

SwiftUI implements this required method of the [ToggleStyle](../ToggleStyle.zh-Hans.md) protocol to define the behavior and appearance of the [switch](../ToggleStyle/switch.zh-Hans.md) toggle style. Don’t call this method directly. Rather, the system calls this method for each [Toggle](../Toggle.zh-Hans.md) instance in a view hierarchy that’s styled as a switch.

