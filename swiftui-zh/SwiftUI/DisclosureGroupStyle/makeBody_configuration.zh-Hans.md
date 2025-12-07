--- 来源：https://developer.apple.com/documentation/SwiftUI/DisclosureGroupStyle/makeBody(configuration:)

抓取时间：2025-12-03T06:11:12Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示披露组主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：要创建的实例的属性。

## 说明

SwiftUI 会针对视图层次结构中创建的每个 [DisclosureGroup](../DisclosureGroup.zh-Hans.md) 实例调用此方法，前提是该视图层次结构中当前样式为 [DisclosureGroupStyle](../DisclosureGroupStyle.zh-Hans.md)。

## 创建自定义披露组样式

- **DisclosureGroupStyleConfiguration**：披露组实例的属性。

- **DisclosureGroupStyle.Configuration**：披露组实例的属性。

- **Body**：表示披露组主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/DisclosureGroupStyle/makeBody(configuration:)
crawled: 2025-12-03T06:11:12Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a disclosure group.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the instance being created.

## Discussion

SwiftUI calls this method for each instance of [DisclosureGroup](../DisclosureGroup.zh-Hans.md) that you create within a view hierarchy where this style is the current [DisclosureGroupStyle](../DisclosureGroupStyle.zh-Hans.md).

## Creating custom disclosure group styles

- **DisclosureGroupStyleConfiguration**: The properties of a disclosure group instance.
- **DisclosureGroupStyle.Configuration**: The properties of a disclosure group instance.
- **Body**: A view that represents the body of a disclosure group.

