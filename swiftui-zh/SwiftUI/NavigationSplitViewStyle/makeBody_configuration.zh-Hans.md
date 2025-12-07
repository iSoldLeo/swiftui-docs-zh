--- 来源：https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle/makeBody(configuration:)

抓取时间：2025-12-03T06:11:17Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示导航拆分视图主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：要创建的实例的属性。

## 说明

SwiftUI 会为每个 [NavigationSplitView](../NavigationSplitView.zh-Hans.md) 实例调用此方法，其中此样式是当前的 [NavigationSplitViewStyle](../NavigationSplitViewStyle.zh-Hans.md)。

## 创建自定义样式

- **NavigationSplitViewStyle.Configuration**：导航拆分视图实例的属性。

- **Body**：表示导航拆分视图主体部分的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/NavigationSplitViewStyle/makeBody(configuration:)
crawled: 2025-12-03T06:11:17Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a navigation split view.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the instance to create.

## Discussion

SwiftUI calls this method for each instance of [NavigationSplitView](../NavigationSplitView.zh-Hans.md), where this style is the current [NavigationSplitViewStyle](../NavigationSplitViewStyle.zh-Hans.md).

## Creating custom styles

- **NavigationSplitViewStyle.Configuration**: The properties of a navigation split view instance.
- **Body**: A view that represents the body of a navigation split view.

