---
来源：https://developer.apple.com/documentation/swiftui/uiviewrepresentable/makeuiview(上下文：)
抓取时间： 2025-12-02T15:07:03Z
---

# makeUIView(context:)

**实例方法**

创建视图对象并配置其初始状态。

## 声明

```swift
@MainActor @preconcurrency func makeUIView(context: Self.Context) -> Self.UIViewType
```

## 参数

- **context**：包含系统当前状态信息的上下文结构。

## 返回值

根据提供的信息配置的 UIKit 视图。

## 讨论

您必须实现此方法并用它来创建视图对象。使用应用程序的当前数据和`context` 参数的内容配置视图。系统只在首次创建视图时调用该方法一次。对于所有后续更新，系统都会调用[updateUIView(_:context:)](updateUIView___context.zh-Hans.md) 方法。

## 创建和更新视图

- **updateUIView(_:context:)**：使用来自 SwiftUI 的新信息更新指定视图的状态。
- **UIViewRepresentable.Context**：使用来自 SwiftUI 的新信息更新指定视图的状态。
- **UIViewType**：要显示的视图类型。


---
source: https://developer.apple.com/documentation/swiftui/uiviewrepresentable/makeuiview(context:)
crawled: 2025-12-02T15:07:03Z
---

# makeUIView(context:)

**Instance Method**

Creates the view object and configures its initial state.

## Declaration

```swift
@MainActor @preconcurrency func makeUIView(context: Self.Context) -> Self.UIViewType
```

## Parameters

- **context**: A context structure containing information about the current state of the system.

## Return Value

Your UIKit view configured with the provided information.

## Discussion

You must implement this method and use it to create your view object. Configure the view using your app’s current data and contents of the `context` parameter. The system calls this method only once, when it creates your view for the first time. For all subsequent updates, the system calls the [updateUIView(_:context:)](updateUIView___context.zh-Hans.md) method.

## Creating and updating the view

- **updateUIView(_:context:)**: Updates the state of the specified view with new information from SwiftUI.
- **UIViewRepresentable.Context**
- **UIViewType**: The type of view to present.

