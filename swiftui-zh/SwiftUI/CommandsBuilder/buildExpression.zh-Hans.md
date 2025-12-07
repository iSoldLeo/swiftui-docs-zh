--- 来源：https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildExpression(_:)

抓取时间：2025-12-01T11:12:34Z

---

# buildExpression(_:)

**类型方法**

在构建器中构建表达式。

## 声明

```swift
static func buildExpression<Content>(_ content: Content) -> Content where Content : Commands
```

## 条件构建

- **buildEither(first:)**：当条件为真时，为多语句闭包中的条件语句生成内容。

- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。

- **buildIf(_:)**：为多语句闭包中的条件语句生成一个可选的组件，该组件仅在条件为真时可见。

- **buildLimitedAvailability(_:)**：处理用于执行可用性检查的条件编译器控制语句的命令。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildExpression(_:)
crawled: 2025-12-01T11:12:34Z
---

# buildExpression(_:)

**Type Method**

Builds an expression within the builder.

## Declaration

```swift
static func buildExpression<Content>(_ content: Content) -> Content where Content : Commands
```

## Building conditionally

- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildIf(_:)**: Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.
- **buildLimitedAvailability(_:)**: Processes commands for a conditional compiler-control statement that performs an availability check.

