---
来源：https://developer.apple.com/documentation/swiftui/nsviewrepresentable/makensview(上下文：)
抓取时间： 2025-12-04T11:33:35Z
---

# makeNSView(context:)

**实例方法**

创建视图对象并配置其初始状态。

## 声明

```swift
@MainActor @preconcurrency func makeNSView(context: Self.Context) -> Self.NSViewType
```

## 参数

- **context**：包含系统当前状态信息的上下文结构。

## 返回值

根据提供的信息配置的 AppKit 视图。

## 讨论

您必须实现此方法并用它来创建视图对象。使用应用程序的当前数据和`context` 参数的内容配置视图。系统只在首次创建视图时调用该方法一次。对于所有后续更新，系统都会调用[updateNSView(_:context:)](../NSViewRepresentable/updateNSView___context.zh-Hans.md) 方法。

## 创建和更新视图

- **updateNSView(_:context:)**：使用来自 SwiftUI 的新信息更新指定视图的状态。
- **NSViewRepresentable.Context**：使用来自 SwiftUI 的新信息更新指定视图的状态。
- **NSViewType**：要显示的视图类型。


---
source: https://developer.apple.com/documentation/swiftui/nsviewrepresentable/makensview(context:)
crawled: 2025-12-04T11:33:35Z
---

# makeNSView(context:)

**Instance Method**

Creates the view object and configures its initial state.

## Declaration

```swift
@MainActor @preconcurrency func makeNSView(context: Self.Context) -> Self.NSViewType
```

## Parameters

- **context**: A context structure containing information about the current state of the system.

## Return Value

Your AppKit view configured with the provided information.

## Discussion

You must implement this method and use it to create your view object. Configure the view using your app’s current data and contents of the `context` parameter. The system calls this method only once, when it creates your view for the first time. For all subsequent updates, the system calls the [updateNSView(_:context:)](../NSViewRepresentable/updateNSView___context.zh-Hans.md) method.

## Creating and updating the view

- **updateNSView(_:context:)**: Updates the state of the specified view with new information from SwiftUI.
- **NSViewRepresentable.Context**
- **NSViewType**: The type of view to present.

