--- 来源：https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/makeBody(configuration:)

抓取时间：2025-12-03T06:11:30Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示控件组主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：要创建的控件组实例的属性。

## 说明

对于视图层次结构中创建的每个 [ControlGroup](../ControlGroup.zh-Hans.md) 实例，如果当前样式为 `ControlGroupStyle`，则会调用此方法。

## 创建自定义控件组样式

- **ControlGroupStyle.Configuration**：正在创建的 `ControlGroup` 实例的属性。

- **Body**：表示控件组主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlGroupStyle/makeBody(configuration:)
crawled: 2025-12-03T06:11:30Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view representing the body of a control group.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the control group instance being created.

## Discussion

This method will be called for each instance of [ControlGroup](../ControlGroup.zh-Hans.md) created within a view hierarchy where this style is the current `ControlGroupStyle`.

## Creating custom control group styles

- **ControlGroupStyle.Configuration**: The properties of a `ControlGroup` instance being created.
- **Body**: A view representing the body of a control group.

