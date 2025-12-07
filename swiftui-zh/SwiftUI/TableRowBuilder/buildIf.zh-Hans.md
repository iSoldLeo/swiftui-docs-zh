---
来源： https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildIf(_:)
抓取时间： 2025-12-03T06:41:37Z
---

# buildIf(_:)

**类型方法**

为条件语句创建行结果。

## 声明

```swift
static func buildIf<C>(_ content: C?) -> C? where Value == C.TableRowValue, C : TableRowContent
```

## 讨论

本方法为多语句闭包中的 "if "语句提供支持，产生的可选值只有在条件求值为`true`时才可见。

## 从条件中建立一行

- **buildEither(first:)**：为两个行内容选项中的第一个创建行结果。
- **buildEither(second:)**：为两个行内容备选方案中的第二个创建行结果。
- **buildExpression(_:)**：在构建器中构建表达式。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildIf(_:)
crawled: 2025-12-03T06:41:37Z
---

# buildIf(_:)

**Type Method**

Creates a row result for conditional statements.

## Declaration

```swift
static func buildIf<C>(_ content: C?) -> C? where Value == C.TableRowValue, C : TableRowContent
```

## Discussion

This method provides support for “if” statements in multi-statement closures, producing an optional value that is visible only when the condition evaluates to `true`.

## Building a row from conditionals

- **buildEither(first:)**: Creates a row result for the first of two row content alternatives.
- **buildEither(second:)**: Creates a row result for the second of two row content alternatives.
- **buildExpression(_:)**: Builds an expression within the builder.

