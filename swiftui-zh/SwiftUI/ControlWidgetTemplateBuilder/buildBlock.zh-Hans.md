---
来源： https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplateBuilder/buildBlock(_:)
抓取时间： 2025-12-03T06:06:29Z
---

# buildBlock(_:)

**类型方法**

将作为子视图写入的单个控件部件模板原封不动地传入。

## 声明

```swift
static func buildBlock<Content>(_ content: Content) -> some ControlWidgetTemplate where Content : ControlWidgetTemplate

```

## 讨论

`{ ControlWidgetToggle(...) }`是一个将单一控件部件模板写成子视图的示例。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetTemplateBuilder/buildBlock(_:)
crawled: 2025-12-03T06:06:29Z
---

# buildBlock(_:)

**Type Method**

Passes a single control widget template written as a child view through unmodified.

## Declaration

```swift
static func buildBlock<Content>(_ content: Content) -> some ControlWidgetTemplate where Content : ControlWidgetTemplate

```

## Discussion

An example of a single control widget template written as a child view is `{ ControlWidgetToggle(...) }`.

