--- 来源：https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildEither(first:)

抓取时间：2025-12-01T11:12:31Z

---

# buildEither(first:)

**类型方法**

当条件为真时，为多语句闭包中的条件语句生成内容。

## 声明

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where T : Commands, F : Commands
```

## 条件构建

- **buildEither(second:)**：当条件为假时，为多语句闭包中的条件语句生成内容。

- **buildIf(_:)**：为多语句闭包中的条件语句生成一个可选组件，该组件仅在条件为真时可见。

- **buildLimitedAvailability(_:)**：处理用于执行可用性检查的条件编译器控制语句的命令。

- **buildExpression(_:)**：在构建器中构建表达式。


---
source: https://developer.apple.com/documentation/SwiftUI/CommandsBuilder/buildEither(first:)
crawled: 2025-12-01T11:12:31Z
---

# buildEither(first:)

**Type Method**

Produces content for a conditional statement in a multi-statement closure when the condition is true.

## Declaration

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where T : Commands, F : Commands
```

## Building conditionally

- **buildEither(second:)**: Produces content for a conditional statement in a multi-statement closure when the condition is false.
- **buildIf(_:)**: Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.
- **buildLimitedAvailability(_:)**: Processes commands for a conditional compiler-control statement that performs an availability check.
- **buildExpression(_:)**: Builds an expression within the builder.

