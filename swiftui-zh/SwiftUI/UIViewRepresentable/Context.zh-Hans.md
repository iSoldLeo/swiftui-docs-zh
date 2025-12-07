---
来源： https://developer.apple.com/documentation/SwiftUI/UIViewRepresentable/Context
抓取时间： 2025-12-03T05:38:51Z
---

# UIViewRepresentable.Context | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ UIViewRepresentable ](/documentation/swiftui/uiviewrepresentable)

- [ UIViewRepresentable.Context ](/documentation/SwiftUI/UIViewRepresentable/Context)

- [ UIViewRepresentable ](/documentation/swiftui/uiviewrepresentable)

- UIViewRepresentable.Context

类型别名# UIViewRepresentable.Context

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
typealias Context = UIViewRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/UIViewRepresentable/Context#see-also)

### [创建和更新视图](/documentation/SwiftUI/UIViewRepresentable/Context#Creating-and-updating-the-view)

[`func makeUIView(context: Self.Context) -> Self.UIViewType`](/documentation/swiftui/uiviewrepresentable/makeuiview(context:))创建视图对象并配置其初始状态。

[`func updateUIView(Self.UIViewType, context: Self.Context)`](/documentation/swiftui/uiviewrepresentable/updateuiview(_:context:))使用来自 SwiftUI 的新信息更新指定视图的状态。

[`associatedtype UIViewType : UIView`](/documentation/swiftui/uiviewrepresentable/uiviewtype)要显示的视图类型。

---
source: https://developer.apple.com/documentation/SwiftUI/UIViewRepresentable/Context
crawled: 2025-12-03T05:38:51Z
---

# UIViewRepresentable.Context | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ UIViewRepresentable ](/documentation/swiftui/uiviewrepresentable)

- [ UIViewRepresentable.Context ](/documentation/SwiftUI/UIViewRepresentable/Context)

- [ UIViewRepresentable ](/documentation/swiftui/uiviewrepresentable)

-  UIViewRepresentable.Context 

Type Alias# UIViewRepresentable.Context

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
typealias Context = UIViewRepresentableContext<Self>
```

## [See Also](/documentation/SwiftUI/UIViewRepresentable/Context#see-also)

### [Creating and updating the view](/documentation/SwiftUI/UIViewRepresentable/Context#Creating-and-updating-the-view)

[`func makeUIView(context: Self.Context) -> Self.UIViewType`](/documentation/swiftui/uiviewrepresentable/makeuiview(context:))Creates the view object and configures its initial state.**Required**

[`func updateUIView(Self.UIViewType, context: Self.Context)`](/documentation/swiftui/uiviewrepresentable/updateuiview(_:context:))Updates the state of the specified view with new information from SwiftUI.**Required**

[`associatedtype UIViewType : UIView`](/documentation/swiftui/uiviewrepresentable/uiviewtype)The type of view to present.**Required**