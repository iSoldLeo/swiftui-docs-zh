---
来源： https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildExpression(_:)
抓取时间： 2025-12-01T11:30:56Z
---

# buildExpression(_:)

**类型方法**

在构建器中构建表达式。

## 声明

```swift
static func buildExpression<Content>(_ content: Content) -> Content where Value == Content.TableRowValue, Content : TableRowContent
```

## 从条件中建立一行

- **buildIf(_:)**：为条件语句创建行结果。
- **buildEither(first:)**：为两个行内容备选方案中的第一个创建行结果。
- **buildEither(second:)**：为两个行内容备选方案中的第二个创建行结果。


---
source: https://developer.apple.com/documentation/SwiftUI/TableRowBuilder/buildExpression(_:)
crawled: 2025-12-01T11:30:56Z
---

# buildExpression(_:)

**Type Method**

Builds an expression within the builder.

## Declaration

```swift
static func buildExpression<Content>(_ content: Content) -> Content where Value == Content.TableRowValue, Content : TableRowContent
```

## Building a row from conditionals

- **buildIf(_:)**: Creates a row result for conditional statements.
- **buildEither(first:)**: Creates a row result for the first of two row content alternatives.
- **buildEither(second:)**: Creates a row result for the second of two row content alternatives.

