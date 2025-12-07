---
来源： https://developer.apple.com/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:)
抓取时间：2025-12-03T06:59:17Z
---

# preferredContentSizeDidChange(forChildContentContainer:) | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

- [ preferredContentSizeDidChange(forChildContentContainer:) ](/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:))

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

- preferredContentSizeDidChange(forChildContentContainer:)

实例方法# preferredContentSizeDidChange(forChildContentContainer:)

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
@MainActor @preconcurrency
override dynamic func preferredContentSizeDidChange(forChildContentContainer container: any UIContentContainer)
```

## [See Also](/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:)#see-also)

### [Managing the size](/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:)#Managing-the-size)

[`var sizingOptions: UIHostingControllerSizingOptions`](/documentation/swiftui/uihostingcontroller/sizingoptions)托管控制器如何跟踪其 SwiftUI 内容大小变化的选项。[`func sizeThatFits(in: CGSize) -> CGSize`](/documentation/swiftui/uihostingcontroller/sizethatfits(in:)计算并返回最适合当前视图的大小。 [`var safeAreaRegions: SafeAreaRegions`](/documentation/swiftui/uihostingcontroller/safearearegions)此视图控制器添加到其视图的安全区域。

---
source: https://developer.apple.com/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:)
crawled: 2025-12-03T06:59:17Z
---

# preferredContentSizeDidChange(forChildContentContainer:) | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

- [ preferredContentSizeDidChange(forChildContentContainer:) ](/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:))

- [ UIHostingController ](/documentation/swiftui/uihostingcontroller)

-  preferredContentSizeDidChange(forChildContentContainer:) 

Instance Method# preferredContentSizeDidChange(forChildContentContainer:)

iOS 13.0+iPadOS 13.0+Mac Catalyst 13.0+tvOS 13.0+visionOS 1.0+

```
@MainActor @preconcurrency
override dynamic func preferredContentSizeDidChange(forChildContentContainer container: any UIContentContainer)
```

## [See Also](/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:)#see-also)

### [Managing the size](/documentation/SwiftUI/UIHostingController/preferredContentSizeDidChange(forChildContentContainer:)#Managing-the-size)

[`var sizingOptions: UIHostingControllerSizingOptions`](/documentation/swiftui/uihostingcontroller/sizingoptions)The options for how the hosting controller tracks changes to the size of its SwiftUI content.[`func sizeThatFits(in: CGSize) -> CGSize`](/documentation/swiftui/uihostingcontroller/sizethatfits(in:))Calculates and returns the most appropriate size for the current view.[`var safeAreaRegions: SafeAreaRegions`](/documentation/swiftui/uihostingcontroller/safearearegions)The safe area regions that this view controller adds to its view.