---
来源： https://developer.apple.com/documentation/SwiftUI/NSViewRepresentable/Context
抓取时间： 2025-12-03T05:38:02Z
---

# NSViewRepresentable.Context | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ NSViewRepresentable ](/documentation/swiftui/nsviewrepresentable)

- [ NSViewRepresentable.Context ](/documentation/SwiftUI/NSViewRepresentable/Context)

- [ NSViewRepresentable ](/documentation/swiftui/nsviewrepresentable)

- NSViewRepresentable.Context

类型别名# NSViewRepresentable.Context

macOS 10.15+

```
typealias Context = NSViewRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/NSViewRepresentable/Context#see-also)

### [创建和更新视图](/documentation/SwiftUI/NSViewRepresentable/Context#Creating-and-updating-the-view)

[`func makeNSView(context: Self.Context) -> Self.NSViewType`](/documentation/swiftui/nsviewrepresentable/makensview(context:))创建视图对象并配置其初始状态。

[`func updateNSView(Self.NSViewType, context: Self.Context)`](/documentation/swiftui/nsviewrepresentable/updatensview(_:context:))使用来自 SwiftUI 的新信息更新指定视图的状态。

[`associatedtype NSViewType : NSView`](/documentation/swiftui/nsviewrepresentable/nsviewtype)要显示的视图类型。

---
source: https://developer.apple.com/documentation/SwiftUI/NSViewRepresentable/Context
crawled: 2025-12-03T05:38:02Z
---

# NSViewRepresentable.Context | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ NSViewRepresentable ](/documentation/swiftui/nsviewrepresentable)

- [ NSViewRepresentable.Context ](/documentation/SwiftUI/NSViewRepresentable/Context)

- [ NSViewRepresentable ](/documentation/swiftui/nsviewrepresentable)

-  NSViewRepresentable.Context 

Type Alias# NSViewRepresentable.Context

macOS 10.15+

```
typealias Context = NSViewRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/NSViewRepresentable/Context#see-also)

### [Creating and updating the view](/documentation/SwiftUI/NSViewRepresentable/Context#Creating-and-updating-the-view)

[`func makeNSView(context: Self.Context) -> Self.NSViewType`](/documentation/swiftui/nsviewrepresentable/makensview(context:))Creates the view object and configures its initial state.**Required**

[`func updateNSView(Self.NSViewType, context: Self.Context)`](/documentation/swiftui/nsviewrepresentable/updatensview(_:context:))Updates the state of the specified view with new information from SwiftUI.**Required**

[`associatedtype NSViewType : NSView`](/documentation/swiftui/nsviewrepresentable/nsviewtype)The type of view to present.**Required**