---
来源：https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildEither(first:)
抓取时间： 2025-12-03T06:41:38Z
---

# buildEither(first:)

**类型方法**

为两个行内容备选方案中的第一个创建行结果。

## 声明

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where Value == T.TableRowValue, T : TableRowContent, F : TableRowContent, T.TableRowValue == F.TableRowValue
```

## 讨论

本方法支持多语句闭包中的 "if "语句，为 "then "分支生成条件内容。

## 从条件中建立一行

- **buildIf(_:)**：为条件语句创建行结果。
- **buildEither(second:)**：为两个行内容选项中的第二个选项创建行结果。
- **buildExpression(_:)**：在构建器中构建表达式。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildEither(first:)
crawled: 2025-12-03T06:41:38Z
---

# buildEither(first:)

**Type Method**

Creates a row result for the first of two row content alternatives.

## Declaration

```swift
static func buildEither<T, F>(first: T) -> _ConditionalContent<T, F> where Value == T.TableRowValue, T : TableRowContent, F : TableRowContent, T.TableRowValue == F.TableRowValue
```

## Discussion

This method provides support for “if” statements in multi-statement closures, producing conditional content for the “then” branch.

## Building a row from conditionals

- **buildIf(_:)**: Creates a row result for conditional statements.
- **buildEither(second:)**: Creates a row result for the second of two row content alternatives.
- **buildExpression(_:)**: Builds an expression within the builder.

