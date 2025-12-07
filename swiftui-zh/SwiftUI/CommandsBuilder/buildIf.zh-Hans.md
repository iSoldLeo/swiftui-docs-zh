--- 来源：https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildIf(_:)

抓取时间：2025-12-03T06:23:29Z

---

# buildIf(_:)

**类型方法**

为多语句闭包中的条件语句生成一个可选组件，该组件仅在条件为真时可见。

## 声明

```swift
static func buildIf<C>(_ content: C?) -> C? where C : Commands
```

## 条件构建

- **buildEither(first:)**：当条件为真时，为多语句闭包中的条件语句生成内容。

- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。

- **buildLimitedAvailability(_:)**：处理用于执行可用性检查的条件编译器控制语句的命令。

- **buildExpression(_:)**：在构建器中构建表达式。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildIf(_:)
crawled: 2025-12-03T06:23:29Z
---

# buildIf(_:)

**Type Method**

Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

## Declaration

```swift
static func buildIf<C>(_ content: C?) -> C? where C : Commands
```

## Building conditionally

- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildLimitedAvailability(_:)**: Processes commands for a conditional compiler-control statement that performs an availability check.
- **buildExpression(_:)**: Builds an expression within the builder.

