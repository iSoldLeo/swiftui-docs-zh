---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder/buildLimitedAvailability(_:)
抓取时间： 2025-12-03T07:13:18Z
---

# buildLimitedAvailability(_:)

**类型方法**

在构建器中构建可用性检查

## 声明

```swift
static func buildLimitedAvailability(_ widget: some ControlWidget) -> any Widget & _LimitedAvailabilityWidgetMarker
```

## 绑定部件

- **buildBlock()**：`{ }`：从一个不包含任何语句的代码块中创建一个空 Widget。
- **buildBlock(_:)**：通过未修改的方式，构建作为子视图（如`{ MyWidget() }`）写入的单个 Widget。
- **buildExpression(_:)**：在构建器中构建表达式。
- **buildOptional(_:)**：为多语句闭包中的条件语句生成一个可选的 widget，该 widget 仅在条件求值为 true 时可见。


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder/buildLimitedAvailability(_:)
crawled: 2025-12-03T07:13:18Z
---

# buildLimitedAvailability(_:)

**Type Method**

Builds an availability check within the builder

## Declaration

```swift
static func buildLimitedAvailability(_ widget: some ControlWidget) -> any Widget & _LimitedAvailabilityWidgetMarker
```

## Bundling widgets

- **buildBlock()**: Builds an empty Widget from a block containing no statements, `{ }`.
- **buildBlock(_:)**: Builds a single Widget written as a child view (e..g, `{ MyWidget() }`) through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildOptional(_:)**: Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

