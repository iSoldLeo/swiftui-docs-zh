---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingController/preferredContentSize
抓取时间： 2025-12-03T06:50:41Z
---

# 首选内容大小 | 苹果开发者文档

- [ SwiftUI ](/documentation/swiftui)

- [ NSHostingController ](/documentation/swiftui/nshostingcontroller)

- [ preferredContentSize ](/documentation/SwiftUI/NSHostingController/preferredContentSize)

- [ NSHostingController ](/documentation/swiftui/nshostingcontroller)

- 首选内容大小

实例属性# preferredContentSize

macOS 10.15+

```
@MainActor @preconcurrency
override dynamic var preferredContentSize: NSSize { get set }
```

## [See Also](/documentation/SwiftUI/NSHostingController/preferredContentSize#see-also)

### [配置控制器](/documentation/SwiftUI/NSHostingController/preferredContentSize#Configuring-the-controller)

[`func sizeThatFits(in: CGSize) -> CGSize`](/documentation/swiftui/nshostingcontroller/sizethatfits(in:)计算并返回当前视图最合适的大小。 [`var sizingOptions: NSHostingSizingOptions`](/documentation/swiftui/nshostingcontroller/sizingoptions)托管控制器的视图如何根据其 SwiftUI 内容的大小创建和更新约束的选项。[`var safeAreaRegions: SafeAreaRegions`](/documentation/swiftui/nshostingcontroller/safearearegions)该视图控制器添加到其视图的安全区域。 [`var sceneBridgingOptions: NSHostingSceneBridgingOptions`](/documentation/swiftui/nshostingcontroller/scenebridgingoptions)该控制器的托管视图将管理窗口的哪些方面的选项。

---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingController/preferredContentSize
crawled: 2025-12-03T06:50:41Z
---

# preferredContentSize | Apple Developer Documentation

- [ SwiftUI ](/documentation/swiftui)

- [ NSHostingController ](/documentation/swiftui/nshostingcontroller)

- [ preferredContentSize ](/documentation/SwiftUI/NSHostingController/preferredContentSize)

- [ NSHostingController ](/documentation/swiftui/nshostingcontroller)

-  preferredContentSize 

Instance Property# preferredContentSize

macOS 10.15+

```
@MainActor @preconcurrency
override dynamic var preferredContentSize: NSSize { get set }
```

## [See Also](/documentation/SwiftUI/NSHostingController/preferredContentSize#see-also)

### [Configuring the controller](/documentation/SwiftUI/NSHostingController/preferredContentSize#Configuring-the-controller)

[`func sizeThatFits(in: CGSize) -> CGSize`](/documentation/swiftui/nshostingcontroller/sizethatfits(in:))Calculates and returns the most appropriate size for the current view.[`var sizingOptions: NSHostingSizingOptions`](/documentation/swiftui/nshostingcontroller/sizingoptions)The options for how the hosting controller’s view creates and updates constraints based on the size of its SwiftUI content.[`var safeAreaRegions: SafeAreaRegions`](/documentation/swiftui/nshostingcontroller/safearearegions)The safe area regions that this view controller adds to its view.[`var sceneBridgingOptions: NSHostingSceneBridgingOptions`](/documentation/swiftui/nshostingcontroller/scenebridgingoptions)The options for which aspects of the window will be managed by this controller’s hosting view.