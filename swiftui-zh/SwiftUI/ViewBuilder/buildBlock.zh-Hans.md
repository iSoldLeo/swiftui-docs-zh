---
来源： https://developer.apple.com/documentation/SwiftUI/ViewBuilder/buildBlock(_:)
抓取时间： 2025-12-02T17:46:13Z
---

# buildBlock(_:)

**类型 方法**

将作为子视图写入的单个视图原封不动地传入。

## 声明

```swift
static func buildBlock<Content>(_ content: Content) -> Content where Content : View
```

## 讨论

`{ Text("Hello") }`是一个将单一视图写成子视图的例子。

## 构建内容

- **buildBlock()**：从一个不包含任何语句的代码块构建一个空视图。
- **buildExpression(_:)**：在构建器中构建表达式。


---
source: https://developer.apple.com/documentation/SwiftUI/ViewBuilder/buildBlock(_:)
crawled: 2025-12-02T17:46:13Z
---

# buildBlock(_:)

**Type Method**

Passes a single view written as a child view through unmodified.

## Declaration

```swift
static func buildBlock<Content>(_ content: Content) -> Content where Content : View
```

## Discussion

An example of a single view written as a child view is `{ Text("Hello") }`.

## Building content

- **buildBlock()**: Builds an empty view from a block containing no statements.
- **buildExpression(_:)**: Builds an expression within the builder.

