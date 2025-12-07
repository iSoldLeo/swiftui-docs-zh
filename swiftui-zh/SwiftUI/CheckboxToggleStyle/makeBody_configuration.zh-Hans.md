--- 来源：https://developer.apple.com/documentation/SwiftUI/CheckboxToggleStyle/makeBody(configuration:)

抓取时间：2025-12-04T13:11:31Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示切换复选框主体的视图。

## 声明

```swift
@MainActor @preconcurrency func makeBody(configuration: CheckboxToggleStyle.Configuration) -> some View

```

## 参数

- **configuration**：切换复选框的属性，包括标签和状态绑定。

## 返回值

一个表示复选框的视图。

## 说明

SwiftUI 实现了 [ToggleStyle](../ToggleStyle.zh-Hans.md) 协议的此必需方法，以定义 [checkbox](../ToggleStyle/checkbox.zh-Hans.md) 切换样式的行为和外观。不要直接调用此方法。系统会针对视图层级结构中每个样式设置为复选框的 [Toggle](../Toggle.zh-Hans.md) 实例调用此方法。


---
source: https://developer.apple.com/documentation/SwiftUI/CheckboxToggleStyle/makeBody(configuration:)
crawled: 2025-12-04T13:11:31Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a toggle checkbox.

## Declaration

```swift
@MainActor @preconcurrency func makeBody(configuration: CheckboxToggleStyle.Configuration) -> some View

```

## Parameters

- **configuration**: The properties of the toggle, including a label and a binding to the toggle’s state.

## Return Value

A view that represents a checkbox.

## Discussion

SwiftUI implements this required method of the [ToggleStyle](../ToggleStyle.zh-Hans.md) protocol to define the behavior and appearance of the [checkbox](../ToggleStyle/checkbox.zh-Hans.md) toggle style. Don’t call this method directly. Rather, the system calls this method for each [Toggle](../Toggle.zh-Hans.md) instance in a view hierarchy that’s styled as a checkbox.

