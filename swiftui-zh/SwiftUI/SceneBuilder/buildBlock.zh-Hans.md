--- 来源：https://developer.apple.com/documentation/SwiftUI/SceneBuilder/buildBlock(_:)

抓取时间：2025-12-03T05:31:11Z

---

# buildBlock(_:)

**类型方法**

将作为子场景编写的单个场景原封不动地传递。

## 声明

```swift
static func buildBlock<Content>(_ content: Content) -> Content where Content : Scene
```

## 构建内容

- **buildExpression(_:)**：在构建器中构建表达式。

- **buildLimitedAvailability(_:)**：处理用于执行可用性检查的条件编译器控制语句的场景内容。

- **buildOptional(_:)**：为多语句闭包中的条件语句生成一个可选场景，该场景仅在条件为真时可见。


---
source: https://developer.apple.com/documentation/SwiftUI/SceneBuilder/buildBlock(_:)
crawled: 2025-12-03T05:31:11Z
---

# buildBlock(_:)

**Type Method**

Passes a single scene written as a child scene through unmodified.

## Declaration

```swift
static func buildBlock<Content>(_ content: Content) -> Content where Content : Scene
```

## Building content

- **buildExpression(_:)**: Builds an expression within the builder.
- **buildLimitedAvailability(_:)**: Processes scene content for a conditional compiler-control statement that performs an availability check.
- **buildOptional(_:)**: Produces an optional scene for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

