---
来源： https://developer.apple.com/documentation/SwiftUI/UIViewControllerRepresentable/Context
抓取时间： 2025-12-03T05:38:33Z
---

# UIViewControllerRepresentable.Context | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ UIViewControllerRepresentable ](/documentation/swiftui/uiviewcontrollerrepresentable)

- [ UIViewControllerRepresentable.Context ](/documentation/SwiftUI/UIViewControllerRepresentable/Context)

- [ UIViewControllerRepresentable ](/documentation/swiftui/uiviewcontrollerrepresentable)

- UIViewControllerRepresentable.Context

类型别名# UIViewControllerRepresentable.Context

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
typealias Context = UIViewControllerRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/UIViewControllerRepresentable/Context#see-also)

### [创建和更新视图控制器](/documentation/SwiftUI/UIViewControllerRepresentable/Context#Creating-and-updating-the-view-controller)

[`func makeUIViewController(context: Self.Context) -> Self.UIViewControllerType`](/documentation/swiftui/uiviewcontrollerrepresentable/makeuiviewcontroller(context:))创建视图控制器对象并配置其初始状态。

[`func updateUIViewController(Self.UIViewControllerType, context: Self.Context)`](/documentation/swiftui/uiviewcontrollerrepresentable/updateuiviewcontroller(_:context:))使用来自 SwiftUI 的新信息更新指定视图控制器的状态。

[`associatedtype UIViewControllerType : UIViewController`](/documentation/swiftui/uiviewcontrollerrepresentable/uiviewcontrollertype)要显示的视图控制器类型。

---
source: https://developer.apple.com/documentation/SwiftUI/UIViewControllerRepresentable/Context
crawled: 2025-12-03T05:38:33Z
---

# UIViewControllerRepresentable.Context | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ UIViewControllerRepresentable ](/documentation/swiftui/uiviewcontrollerrepresentable)

- [ UIViewControllerRepresentable.Context ](/documentation/SwiftUI/UIViewControllerRepresentable/Context)

- [ UIViewControllerRepresentable ](/documentation/swiftui/uiviewcontrollerrepresentable)

-  UIViewControllerRepresentable.Context 

Type Alias# UIViewControllerRepresentable.Context

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
typealias Context = UIViewControllerRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/UIViewControllerRepresentable/Context#see-also)

### [Creating and updating the view controller](/documentation/SwiftUI/UIViewControllerRepresentable/Context#Creating-and-updating-the-view-controller)

[`func makeUIViewController(context: Self.Context) -> Self.UIViewControllerType`](/documentation/swiftui/uiviewcontrollerrepresentable/makeuiviewcontroller(context:))Creates the view controller object and configures its initial state.**Required**

[`func updateUIViewController(Self.UIViewControllerType, context: Self.Context)`](/documentation/swiftui/uiviewcontrollerrepresentable/updateuiviewcontroller(_:context:))Updates the state of the specified view controller with new information from SwiftUI.**Required**

[`associatedtype UIViewControllerType : UIViewController`](/documentation/swiftui/uiviewcontrollerrepresentable/uiviewcontrollertype)The type of view controller to present.**Required**