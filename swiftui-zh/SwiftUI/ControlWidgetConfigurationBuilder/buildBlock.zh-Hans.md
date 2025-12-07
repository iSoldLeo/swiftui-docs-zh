---
来源： https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfigurationBuilder/buildBlock(_:)
抓取时间： 2025-12-03T06:06:17Z
---

# buildBlock(_:)

**类型方法**

将作为子控件写入的单个控件部件配置原封不动地传入。

## 声明

```swift
static func buildBlock<Content>(_ content: Content) -> some ControlWidgetConfiguration where Content : ControlWidgetConfiguration

```

## 讨论

`{ StaticControlConfiguration(...) }`是一个将单一控件部件配置写成子视图的示例。


---
source: https://developer.apple.com/documentation/SwiftUI/ControlWidgetConfigurationBuilder/buildBlock(_:)
crawled: 2025-12-03T06:06:17Z
---

# buildBlock(_:)

**Type Method**

Passes a single control widget configuration written as a child control through unmodified.

## Declaration

```swift
static func buildBlock<Content>(_ content: Content) -> some ControlWidgetConfiguration where Content : ControlWidgetConfiguration

```

## Discussion

An example of a single control widget configuration written as a child view is `{ StaticControlConfiguration(...) }`.

