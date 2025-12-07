---
来源： https://developer.apple.com/documentation/SwiftUI/ViewBuilder/buildExpression(_:)
抓取时间： 2025-12-02T17:46:13Z
---

# buildExpression(_:)

**类型方法**

在构建器中构建表达式。

## 声明

```swift
static func buildExpression<Content>(_ content: Content) -> Content where Content : View
```

## 建设内容

- **buildBlock()**：从一个不包含任何语句的代码块构建一个空视图。
- **buildBlock(_:)**：将作为子视图写入的单个视图原封不动地通过。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewBuilder/buildExpression(_:)
crawled: 2025-12-02T17:46:13Z
---

# buildExpression(_:)

**Type Method**

Builds an expression within the builder.

## Declaration

```swift
static func buildExpression<Content>(_ content: Content) -> Content where Content : View
```

## Building content

- **buildBlock()**: Builds an empty view from a block containing no statements.
- **buildBlock(_:)**: Passes a single view written as a child view through unmodified.

