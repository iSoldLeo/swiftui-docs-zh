---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextValueConstraint
抓取时间： 2025-12-02T17:34:58Z
---

# 属性文本值约束（AttributedTextValueConstraint

**Protocol**

用于定义某一属性值的约束的协议。

### 声明

```swift
protocol AttributedTextValueConstraint : Hashable, Sendable, AttributedTextFormattingDefinition
```

## 概览

作为[AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md)使用，它使用`constrain(_:)-(Attributes)`函数约束[AttributeKey](AttributedTextValueConstraint/AttributeKey.zh-Hans.md)的值。

考虑到值约束可以读取其他属性值，因此必须避免将值约束混合在一起，从而产生具有未定义行为的循环依赖关系。因此，我们建议在考虑值约束时，将其放在将要使用的[AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md) 的上下文中：

一个简单的约束只能访问一个属性。它可以在属性范围内通用，因此可以在不同的[AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md)中重复使用。

```swift
struct NoBlackOrWhiteForeground<Scope: AttributeScope>: AttributedTextValueConstraint {
    typealias AttributeKey = AttributeScopes.SwiftUIAttributes.ForegroundColorAttribute

    func constrain(
        _ container: inout Attributes
    ) {
        if container.foregroundColor == .white || container.foregroundColor == .black {
            container.foregroundColor = .primary
        }
    }
}
```

当约束需要访问其他属性值时，建议将其定义在用于单个[AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md) 的特定属性范围上。

```swift
extension MyTextFormattingDefinition {
    struct Scope: AttributeScope {
        /* ... */
        let foregroundColor: AttributeScopes.SwiftUIAttributes.ForegroundColorAttribute
        let backgroundColor: AttributeScopes.SwiftUIAttributes.BackgroundColorAttribute
    }
}

struct NoEqualForegroundAndBackground: AttributedTextValueConstraint {
    typealias Scope = MyTextFormattingDefinition.Scope
    typealias AttributeKey = AttributeScopes.SwiftUIAttributes.BackgroundColorAttribute

    func constrain(
        _ container: inout Attributes
    ) {
        if let color = container.foregroundColor,
           container.backgroundColor == color
        {
            container.backgroundColor = nil
        }
    }
}
```

访问多个属性并在范围内通用的约束应记录其依赖关系，以便在[body-1b01t](AttributedTextFormattingDefinition/body-1b01t.zh-Hans.md)中对约束排序时考虑这些依赖关系。

```swift
/// Makes the background color for all Genmoji blue.
///
/// - Note: This constraint depends on a valid adaptiveImageGlyph value.
struct BlueGenmojiBackgroundConstraint<Scope: AttributeScope>: AttributedTextValueConstraint {
    typealias AttributeKey = AttributeScopes.SwiftUIAttributes
        .BackgroundColorAttribute

    func constrain(
        _ container: inout Attributes
    ) {
        if container[
            AttributeScopes.SwiftUIAttributes.AdaptiveImageGlyphAttribute.self
        ] != nil {
            container.backgroundColor = .blue
        }
    }
}
```

## 相关类型

- **AttributeKey**：受此约束限制的属性。

### 实例方法

- **constrain(_:)**：对属性执行约束。

### 类型别名

- **AttributedTextValueConstraint.Attributes**：部分约束属性容器的代理类型。

## 控制文本样式

- **bold(_:)**：为该视图中的文本应用粗体字体权重。
- **italic(_:)**：为该视图中的文本应用斜体。
- **underline(_:pattern:color:)**：为该视图中的文本添加下划线。
- **strikethrough(_:pattern:color:)**：为该视图中的文本应用删除线。
- **textCase(_:)**：为该视图中包含的文本在显示时的大小写设置变换。
- **textCase**：样式覆盖，用于在显示`Text` 时使用环境的本地语言转换大小写。
- **monospaced(_:)**：尽可能修改所有子视图的字体，使其使用当前字体的固定宽度变体。
- **monospacedDigit()**：修改所有子视图的字体，尽可能使用固定宽度的数字，同时按比例保留其他字符的间距。
- **AttributedTextFormattingDefinition**：用于定义视图中文本样式的协议。
- **AttributedTextFormatting**：与归属文本格式定义相关类型的命名空间。

## 继承自

- 属性文本格式定义
- 等价
- 可散列
- 可发送
- 可发送元类型

## 符合类型

- 属性文本格式.值约束


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextValueConstraint
crawled: 2025-12-02T17:34:58Z
---

# AttributedTextValueConstraint

**Protocol**

A protocol for defining a constraint on the value of a certain attribute.

## Declaration

```swift
protocol AttributedTextValueConstraint : Hashable, Sendable, AttributedTextFormattingDefinition
```

## Overview

Used as an [AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md), this constrains the [AttributeKey](AttributedTextValueConstraint/AttributeKey.zh-Hans.md)’s value using the `constrain(_:)-(Attributes)` function.

Given value constraints can read other attribute values, it is crucial to avoid mixing value constraints in a way where they create cyclic dependencies with undefined behavior. Thus, it is recommended to think about value constraints in the context of the [AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md) they will be used in:

A simple constraint only accesses a single attribute. It can be made generic over the attribute scope so it can be reused in different [AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md)s.

```swift
struct NoBlackOrWhiteForeground<Scope: AttributeScope>: AttributedTextValueConstraint {
    typealias AttributeKey = AttributeScopes.SwiftUIAttributes.ForegroundColorAttribute

    func constrain(
        _ container: inout Attributes
    ) {
        if container.foregroundColor == .white || container.foregroundColor == .black {
            container.foregroundColor = .primary
        }
    }
}
```

When the constraint needs to access other attribute values, it is recommended to define it on a specific attribute scope that is used for a single [AttributedTextFormattingDefinition](AttributedTextFormattingDefinition.zh-Hans.md).

```swift
extension MyTextFormattingDefinition {
    struct Scope: AttributeScope {
        /* ... */
        let foregroundColor: AttributeScopes.SwiftUIAttributes.ForegroundColorAttribute
        let backgroundColor: AttributeScopes.SwiftUIAttributes.BackgroundColorAttribute
    }
}

struct NoEqualForegroundAndBackground: AttributedTextValueConstraint {
    typealias Scope = MyTextFormattingDefinition.Scope
    typealias AttributeKey = AttributeScopes.SwiftUIAttributes.BackgroundColorAttribute

    func constrain(
        _ container: inout Attributes
    ) {
        if let color = container.foregroundColor,
           container.backgroundColor == color
        {
            container.backgroundColor = nil
        }
    }
}
```

Constraints that access multiple attributes and are generic over the scope should document their dependencies so that the dependencies can be considered for the ordering of constraints in the [body-1b01t](AttributedTextFormattingDefinition/body-1b01t.zh-Hans.md).

```swift
/// Makes the background color for all Genmoji blue.
///
/// - Note: This constraint depends on a valid adaptiveImageGlyph value.
struct BlueGenmojiBackgroundConstraint<Scope: AttributeScope>: AttributedTextValueConstraint {
    typealias AttributeKey = AttributeScopes.SwiftUIAttributes
        .BackgroundColorAttribute

    func constrain(
        _ container: inout Attributes
    ) {
        if container[
            AttributeScopes.SwiftUIAttributes.AdaptiveImageGlyphAttribute.self
        ] != nil {
            container.backgroundColor = .blue
        }
    }
}
```

## Associated Types

- **AttributeKey**: The attribute constrained by this constraint.

## Instance Methods

- **constrain(_:)**: Enforce constraints on the attribute.

## Type Aliases

- **AttributedTextValueConstraint.Attributes**: A proxy type for a container of partially constrained attributes.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextFormattingDefinition**: A protocol for defining how text can be styled in a view.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

## Inherits From

- AttributedTextFormattingDefinition
- Equatable
- Hashable
- Sendable
- SendableMetatype

## Conforming Types

- AttributedTextFormatting.ValueConstraint

