--- 来源：https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildLimitedAvailability(_:)

抓取时间：2025-12-01T11:12:33Z

---

# buildLimitedAvailability(_:)

**类型方法**

处理用于执行可用性检查的条件编译器控制语句的命令。

## 声明

```swift
static func buildLimitedAvailability(_ content: any Commands) -> some Commands

```

## 条件构建

- **buildEither(first:)**：当条件为真时，生成多语句闭包中条件语句的内容。

- **buildEither(second:)**：当条件为假时，生成多语句闭包中条件语句的内容。

- **buildIf(_:)**：为多语句闭包中的条件语句生成一个可选的小部件，该小部件仅在条件为真时可见。

- **buildExpression(_:)**：在构建器中构建表达式。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildLimitedAvailability(_:)
crawled: 2025-12-01T11:12:33Z
---

# buildLimitedAvailability(_:)

**Type Method**

Processes commands for a conditional compiler-control statement that performs an availability check.

## Declaration

```swift
static func buildLimitedAvailability(_ content: any Commands) -> some Commands

```

## Building conditionally

- **buildEither(first:)**: Produces content for a conditional statement in a multi-statement closure when the condition is true.
- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildIf(_:)**: Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.
- **buildExpression(_:)**: Builds an expression within the builder.

