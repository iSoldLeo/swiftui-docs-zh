---
来源： https://developer.apple.com/documentation/SwiftUI/ControlWidget/body-swift.property
抓取时间： 2025-12-03T06:05:59Z
---

# 正文

**实例属性**

控件的内容和行为。

## 声明

```swift
@ControlWidgetConfigurationBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## 讨论

对于您创建的任何控件，请提供一个计算的 `body` 属性，该属性使用一些控件部件配置来定义控件。

Swift 会根据`body` 属性的内容推断控件的[Body-swift.associatedtype](Body-swift_associatedtype.zh-Hans.md) 关联类型。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidget/body-swift.property
crawled: 2025-12-03T06:05:59Z
---

# body

**Instance Property**

The content and behavior of the control.

## Declaration

```swift
@ControlWidgetConfigurationBuilder @MainActor @preconcurrency var body: Self.Body { get }
```

## Discussion

For any controls that you create, provide a computed `body` property that defines the control using some control widget configuration.

Swift infers the control’s [Body-swift.associatedtype](Body-swift_associatedtype.zh-Hans.md) associated type based on the contents of the `body` property.

