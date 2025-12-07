---
来源：https://developer.apple.com/documentation/SwiftUI/UIViewControllerRepresentable/updateUIViewController(_:context:)
抓取时间： 2025-12-03T05:38:28Z
---

# updateUIViewController(_:context:)

**实例方法**

使用 SwiftUI 提供的新信息更新指定视图控制器的状态。

## 声明

```swift
@MainActor @preconcurrency func updateUIViewController(_ uiViewController: Self.UIViewControllerType, context: Self.Context)
```

## 参数

- **uiViewController**：您的自定义视图控制器对象。
- **context**：包含系统当前状态信息的上下文结构。

## 讨论

当应用程序的状态发生变化时，SwiftUI 会更新受这些变化影响的界面部分。对于影响相应 UIKit 视图控制器的任何更改，SwiftUI 都会调用此方法。使用此方法更新视图控制器的配置，以匹配`context` 参数中提供的新状态信息。

## 创建和更新视图控制器

- **makeUIViewController(context:)**：创建视图控制器对象并配置其初始状态。
- **UIViewControllerRepresentable.Context**：创建视图控制器对象并配置其初始状态。
- **UIViewControllerType**：要显示的视图控制器类型。


---
source: https://developer.apple.com/documentation/SwiftUI/UIViewControllerRepresentable/updateUIViewController(_:context:)
crawled: 2025-12-03T05:38:28Z
---

# updateUIViewController(_:context:)

**Instance Method**

Updates the state of the specified view controller with new information from SwiftUI.

## Declaration

```swift
@MainActor @preconcurrency func updateUIViewController(_ uiViewController: Self.UIViewControllerType, context: Self.Context)
```

## Parameters

- **uiViewController**: Your custom view controller object.
- **context**: A context structure containing information about the current state of the system.

## Discussion

When the state of your app changes, SwiftUI updates the portions of your interface affected by those changes. SwiftUI calls this method for any changes affecting the corresponding UIKit view controller. Use this method to update the configuration of your view controller to match the new state information provided in the `context` parameter.

## Creating and updating the view controller

- **makeUIViewController(context:)**: Creates the view controller object and configures its initial state.
- **UIViewControllerRepresentable.Context**
- **UIViewControllerType**: The type of view controller to present.

