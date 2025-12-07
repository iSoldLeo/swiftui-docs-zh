---
来源：https://developer.apple.com/documentation/swiftui/uiviewrepresentable/updateuiview(_:context:)
抓取时间：2025-12-02T15:07:04Z
---

# updateUIView(_:context:)

**实例方法**

使用 SwiftUI 提供的新信息更新指定视图的状态。

## 声明

```swift
@MainActor @preconcurrency func updateUIView(_ uiView: Self.UIViewType, context: Self.Context)
```

## 参数

- **uiView**：您的自定义视图对象。
- **context**：包含系统当前状态信息的上下文结构。

## 讨论

当应用程序的状态发生变化时，SwiftUI 会更新受这些变化影响的界面部分。对于影响相应 UIKit 视图的任何更改，SwiftUI 都会调用此方法。使用此方法可更新视图的配置，以匹配`context` 参数中提供的新状态信息。

## 创建和更新视图

- **makeUIView(context:)**：创建视图对象并配置其初始状态。
- **UIViewRepresentable.Context**：创建视图对象并配置其初始状态。
- **UIViewType**：要显示的视图类型。


---
source: https://developer.apple.com/documentation/swiftui/uiviewrepresentable/updateuiview(_:context:)
crawled: 2025-12-02T15:07:04Z
---

# updateUIView(_:context:)

**Instance Method**

Updates the state of the specified view with new information from SwiftUI.

## Declaration

```swift
@MainActor @preconcurrency func updateUIView(_ uiView: Self.UIViewType, context: Self.Context)
```

## Parameters

- **uiView**: Your custom view object.
- **context**: A context structure containing information about the current state of the system.

## Discussion

When the state of your app changes, SwiftUI updates the portions of your interface affected by those changes. SwiftUI calls this method for any changes affecting the corresponding UIKit view. Use this method to update the configuration of your view to match the new state information provided in the `context` parameter.

## Creating and updating the view

- **makeUIView(context:)**: Creates the view object and configures its initial state.
- **UIViewRepresentable.Context**
- **UIViewType**: The type of view to present.

