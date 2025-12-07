---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder/buildBlock(_:)
抓取时间： 2025-12-01T12:02:14Z
---

# buildBlock(_:)

**类型 方法**

通过未修改的方式，构建作为子视图（如`{ MyWidget() }`）写入的单个 Widget。

## 声明

```swift
static func buildBlock<Content>(_ content: Content) -> some Widget where Content : Widget

```

## 绑定部件

- **buildBlock()**：`{ }`：从一个不包含任何语句的代码块中创建一个空 Widget。
- **buildExpression(_:)**：在构建器中构建表达式。
- **buildLimitedAvailability(_:)**：在构建器中构建可用性检查
- **buildOptional(_:)**：为多语句闭包中的条件语句生成一个可选的 widget，该 widget 仅在条件求值为 true 时可见。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder/buildBlock(_:)
crawled: 2025-12-01T12:02:14Z
---

# buildBlock(_:)

**Type Method**

Builds a single Widget written as a child view (e..g, `{ MyWidget() }`) through unmodified.

## Declaration

```swift
static func buildBlock<Content>(_ content: Content) -> some Widget where Content : Widget

```

## Bundling widgets

- **buildBlock()**: Builds an empty Widget from a block containing no statements, `{ }`.
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildLimitedAvailability(_:)**: Builds an availability check within the builder
- **buildOptional(_:)**: Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

