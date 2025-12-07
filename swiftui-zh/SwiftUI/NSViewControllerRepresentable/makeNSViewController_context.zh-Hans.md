---
来源：https://developer.apple.com/documentation/swiftui/nsviewcontrollerrepresentable/makensviewcontroller(上下文：)
抓取时间： 2025-12-04T11:33:30Z
---

# makeNSViewController(context:)

**实例方法**

创建视图控制器对象并配置其初始状态。

## 声明

```swift
@MainActor @preconcurrency func makeNSViewController(context: Self.Context) -> Self.NSViewControllerType
```

## 参数

- **context**：包含系统当前状态信息的上下文结构。

## 返回值

根据提供的信息配置的 AppKit 视图控制器。

## 讨论

您必须实现此方法并用它来创建视图控制器对象。使用应用程序的当前数据和`context` 参数的内容创建视图控制器。系统只在首次创建视图控制器时调用该方法一次。对于所有后续更新，系统都会调用[updateNSViewController(_:context:)](updatensviewcontroller___context.zh-Hans.md) 方法。

## 创建和更新视图控制器

- **updateNSViewController(_:context:)**方法：使用来自 SwiftUI 的新信息更新指定视图控制器的状态。
- **NSViewControllerRepresentable.Context**：使用来自 SwiftUI 的新信息更新指定视图控制器的状态。
- **NSViewControllerType**：要显示的视图控制器类型。


---
source: https://developer.apple.com/documentation/swiftui/nsviewcontrollerrepresentable/makensviewcontroller(context:)
crawled: 2025-12-04T11:33:30Z
---

# makeNSViewController(context:)

**Instance Method**

Creates the view controller object and configures its initial state.

## Declaration

```swift
@MainActor @preconcurrency func makeNSViewController(context: Self.Context) -> Self.NSViewControllerType
```

## Parameters

- **context**: A context structure containing information about the current state of the system.

## Return Value

Your AppKit view controller configured with the provided information.

## Discussion

You must implement this method and use it to create your view controller object. Create the view controller using your app’s current data and contents of the `context` parameter. The system calls this method only once, when it creates your view controller for the first time. For all subsequent updates, the system calls the [updateNSViewController(_:context:)](updatensviewcontroller___context.zh-Hans.md) method.

## Creating and updating the view controller

- **updateNSViewController(_:context:)**: Updates the state of the specified view controller with new information from SwiftUI.
- **NSViewControllerRepresentable.Context**
- **NSViewControllerType**: The type of view controller to present.

