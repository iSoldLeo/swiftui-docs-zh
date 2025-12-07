---
来源： https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder/buildOptional(_:)
抓取时间： 2025-12-01T12:02:17Z
---

# buildOptional(_:)

**类型方法**

为多语句闭包中的条件语句生成一个可选部件，该部件只有在条件求值为 true 时才可见。

### 声明

```swift
static func buildOptional(_ widget: (any Widget & _LimitedAvailabilityWidgetMarker)?) -> some Widget

```

## 讨论

[WidgetBundleBuilder](../WidgetBundleBuilder.zh-Hans.md)中的条件语句可以包含`if`语句，但不能包含`else`语句，而且条件只能执行编译器的可用性检查，如下面的代码：

```swift
var body: some Widget {
    if #available(iOS 16, *) {
        WindowGroup {
            ContentView()
        }
    }
}
```

## 绑定部件

- **buildBlock()**：`{ }`：从一个不包含任何语句的代码块中创建一个空 Widget。
- **buildBlock(_:)**：通过未修改的方式，构建作为子视图（如`{ MyWidget() }`）写入的单个 Widget。
- **buildExpression(_:)**：在构建器中构建表达式。
- **buildLimitedAvailability(_:)**：在构建器中构建可用性检查


---
source: https://developer.apple.com/documentation/SwiftUI/WidgetBundleBuilder/buildOptional(_:)
crawled: 2025-12-01T12:02:17Z
---

# buildOptional(_:)

**Type Method**

Produces an optional widget for conditional statements in multi-statement closures that’s only visible when the condition evaluates to true.

## Declaration

```swift
static func buildOptional(_ widget: (any Widget & _LimitedAvailabilityWidgetMarker)?) -> some Widget

```

## Discussion

Conditional statements in a [WidgetBundleBuilder](../WidgetBundleBuilder.zh-Hans.md) can contain an `if` statement but not an `else` statement, and the condition can only perform a compiler check for availability, like in the following code:

```swift
var body: some Widget {
    if #available(iOS 16, *) {
        WindowGroup {
            ContentView()
        }
    }
}
```

## Bundling widgets

- **buildBlock()**: Builds an empty Widget from a block containing no statements, `{ }`.
- **buildBlock(_:)**: Builds a single Widget written as a child view (e..g, `{ MyWidget() }`) through unmodified.
- **buildExpression(_:)**: Builds an expression within the builder.
- **buildLimitedAvailability(_:)**: Builds an availability check within the builder

