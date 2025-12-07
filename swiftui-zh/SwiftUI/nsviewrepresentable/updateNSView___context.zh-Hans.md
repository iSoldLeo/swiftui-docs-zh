---
来源：https://developer.apple.com/documentation/swiftui/nsviewrepresentable/updatensview(_:context:)
抓取时间：2025-12-04T11:33:36Z
---

# updateNSView(_:context:)

**实例方法**

使用 SwiftUI 提供的新信息更新指定视图的状态。

## 声明

```swift
@MainActor @preconcurrency func updateNSView(_ nsView: Self.NSViewType, context: Self.Context)
```

## 参数

- **nsView**：您的自定义视图对象。
- **context**：包含系统当前状态信息的上下文结构。

## 讨论

当应用程序的状态发生变化时，SwiftUI 会更新受这些变化影响的界面部分。对于影响相应 AppKit 视图的任何更改，SwiftUI 都会调用此方法。使用此方法可更新视图的配置，以匹配`context` 参数中提供的新状态信息。

## 创建和更新视图

- **makeNSView(context:)**：创建视图对象并配置其初始状态。
- **NSViewRepresentable.Context**：创建视图对象并配置其初始状态。
- **NSViewType**：要显示的视图类型。


---
source: https://developer.apple.com/documentation/swiftui/nsviewrepresentable/updatensview(_:context:)
crawled: 2025-12-04T11:33:36Z
---

# updateNSView(_:context:)

**Instance Method**

Updates the state of the specified view with new information from SwiftUI.

## Declaration

```swift
@MainActor @preconcurrency func updateNSView(_ nsView: Self.NSViewType, context: Self.Context)
```

## Parameters

- **nsView**: Your custom view object.
- **context**: A context structure containing information about the current state of the system.

## Discussion

When the state of your app changes, SwiftUI updates the portions of your interface affected by those changes. SwiftUI calls this method for any changes affecting the corresponding AppKit view. Use this method to update the configuration of your view to match the new state information provided in the `context` parameter.

## Creating and updating the view

- **makeNSView(context:)**: Creates the view object and configures its initial state.
- **NSViewRepresentable.Context**
- **NSViewType**: The type of view to present.

