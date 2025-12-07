---
来源： https://developer.apple.com/documentation/SwiftUI/Widget/body-swift.property
抓取时间： 2025-12-03T06:05:39Z
---

# 正文

**实例属性**

部件的内容和行为。

## 声明

```swift
@MainActor @preconcurrency var body: Self.Body { get }
```

## 讨论

对于您创建的任何 widget，请提供一个计算的 `body` 属性，将 widget 定义为 SwiftUI 视图的组合。

Swift 会根据 `body` 属性的内容推断出 widget 的 [Body-swift.associatedtype](../scene/Body-swift_associatedtype.zh-Hans.md) 关联类型。

## 实现小部件

- **Body**：表示 widget 内容的配置类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Widget/body-swift.property
crawled: 2025-12-03T06:05:39Z
---

# body

**Instance Property**

The content and behavior of the widget.

## Declaration

```swift
@MainActor @preconcurrency var body: Self.Body { get }
```

## Discussion

For any widgets that you create, provide a computed `body` property that defines the widget as a composition of SwiftUI views.

Swift infers the widget’s [Body-swift.associatedtype](../scene/Body-swift_associatedtype.zh-Hans.md) associated type based on the contents of the `body` property.

## Implementing a widget

- **Body**: The type of configuration representing the content of the widget.

