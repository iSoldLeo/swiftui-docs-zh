--- 来源：https://developer.apple.com/documentation/SwiftUI/SceneBuilder/buildLimitedAvailability(_:)

抓取时间：2025-12-01T10:20:18Z

---

# buildLimitedAvailability(_:)

**类型方法**

处理用于执行可用性检查的条件编译器控制语句的场景内容。

## 声明

```swift
static func buildLimitedAvailability(_ scene: some Scene) -> any Scene & _LimitedAvailabilitySceneMarker
```

## 构建内容

- **buildBlock(_:)**：将作为子场景编写的单个场景原封不动地传递。

- **buildExpression(_:)**：在构建器中构建表达式。

- **buildOptional(_:)**：为多语句闭包中的条件语句生成一个可选场景，该场景仅在条件为真时可见。


---
source: https://developer.apple.com/documentation/SwiftUI/SceneBuilder/buildLimitedAvailability(_:)
crawled: 2025-12-01T10:20:18Z
---

# buildLimitedAvailability(_:)

**Type Method**

Processes scene content for a conditional compiler-control statement that performs an availability check.

## Declaration

```swift
static func buildLimitedAvailability(_ scene: some Scene) -> any Scene & _LimitedAvailabilitySceneMarker
```

## Building content

- **buildBlock(_:)**: Passes a single scene written as a child scene through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildOptional(_:)**: Produces an optional scene for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

