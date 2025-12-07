---
来源： https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentable/Context
抓取时间： 2025-12-03T05:37:43Z
---

# NSViewControllerRepresentable.Context | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ NSViewControllerRepresentable ](/documentation/swiftui/nsviewcontrollerrepresentable)

- [ NSViewControllerRepresentable.Context ](/documentation/SwiftUI/NSViewControllerRepresentable/Context)

- [ NSViewControllerRepresentable ](/documentation/swiftui/nsviewcontrollerrepresentable)

- NSViewControllerRepresentable.Context

类型别名# NSViewControllerRepresentable.Context

macOS 10.15+

```
typealias Context = NSViewControllerRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/NSViewControllerRepresentable/Context#see-also)

### [创建和更新视图控制器](/documentation/SwiftUI/NSViewControllerRepresentable/Context#Creating-and-updating-the-view-controller)

[`func makeNSViewController(context: Self.Context) -> Self.NSViewControllerType`](/documentation/swiftui/nsviewcontrollerrepresentable/makensviewcontroller(context:))创建视图控制器对象并配置其初始状态。

[`func updateNSViewController(Self.NSViewControllerType, context: Self.Context)`](/documentation/swiftui/nsviewcontrollerrepresentable/updatensviewcontroller(_:context:))使用来自 SwiftUI 的新信息更新指定视图控制器的状态。

[`associatedtype NSViewControllerType : NSViewController`](/documentation/swiftui/nsviewcontrollerrepresentable/nsviewcontrollertype)要显示的视图控制器类型。

---
source: https://developer.apple.com/documentation/SwiftUI/NSViewControllerRepresentable/Context
crawled: 2025-12-03T05:37:43Z
---

# NSViewControllerRepresentable.Context | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ NSViewControllerRepresentable ](/documentation/swiftui/nsviewcontrollerrepresentable)

- [ NSViewControllerRepresentable.Context ](/documentation/SwiftUI/NSViewControllerRepresentable/Context)

- [ NSViewControllerRepresentable ](/documentation/swiftui/nsviewcontrollerrepresentable)

-  NSViewControllerRepresentable.Context 

Type Alias# NSViewControllerRepresentable.Context

macOS 10.15+

```
typealias Context = NSViewControllerRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/NSViewControllerRepresentable/Context#see-also)

### [Creating and updating the view controller](/documentation/SwiftUI/NSViewControllerRepresentable/Context#Creating-and-updating-the-view-controller)

[`func makeNSViewController(context: Self.Context) -> Self.NSViewControllerType`](/documentation/swiftui/nsviewcontrollerrepresentable/makensviewcontroller(context:))Creates the view controller object and configures its initial state.**Required**

[`func updateNSViewController(Self.NSViewControllerType, context: Self.Context)`](/documentation/swiftui/nsviewcontrollerrepresentable/updatensviewcontroller(_:context:))Updates the state of the specified view controller with new information from SwiftUI.**Required**

[`associatedtype NSViewControllerType : NSViewController`](/documentation/swiftui/nsviewcontrollerrepresentable/nsviewcontrollertype)The type of view controller to present.**Required**