---
来源：https://developer.apple.com/documentation/SwiftUI/GroupBoxStyle/makeBody(配置：)
抓取时间：2025-12-01T11:00:44Z
---

# makeBody(configuration:)

**实例方法**

创建代表组框主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：正在创建的分组框实例的属性。

## 讨论

SwiftUI 会为视图层次结构中创建的每个⟦DL_0002❾ 实例调用此方法，其中此样式是当前的组框样式。

## 创建自定义组框样式

- **GroupBoxStyle.Configuration**：组框实例的属性。
- **Body**：表示组方框主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/GroupBoxStyle/makeBody(configuration:)
crawled: 2025-12-01T11:00:44Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view representing the body of a group box.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the group box instance being created.

## Discussion

SwiftUI calls this method for each instance of [GroupBox](../GroupBox.zh-Hans.md) created within a view hierarchy where this style is the current group box style.

## Creating custom group box styles

- **GroupBoxStyle.Configuration**: The properties of a group box instance.
- **Body**: A view that represents the body of a group box.

