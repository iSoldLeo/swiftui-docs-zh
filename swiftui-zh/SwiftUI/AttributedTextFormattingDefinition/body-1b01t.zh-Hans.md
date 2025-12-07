---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextFormattingDefinition/body-1b01t
抓取时间： 2025-12-03T06:18:39Z
---

# 正文

**实例属性**

格式化定义的约束条件。

## 声明

```swift
@AttributedTextFormatting.DefinitionBuilder<Self.Scope> var body: Self.Body { get }
```

## 讨论

当您实现自定义定义时，您必须实现一个计算的 `body` 属性，以提供定义的约束条件。返回一个由 SwiftUI 提供的内置定义（如[ValueConstraint](ValueConstraint.zh-Hans.md) 和 [AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md)）以及您已定义的其他复合[AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md)）组成的定义：

```swift
struct MyTextFormattingDefinition: AttributedTextFormattingDefinition {
    var body: some AttributedTextFormattingDefinition<
        AttributeScopes.SwiftUIAttributes
    > {
        ValueConstraint(
            for: \.underlineStyle,
            values: [nil, .single],
            default: .single)
        MyAttributedTextValueConstraint()
    }
}
```

请注意，结果生成器中约束的顺序很重要，因为约束是按顺序应用的。有关详情，请参阅 `AttributedTextValueConstraint/constrain(_:)-(Attributes)`。


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormattingDefinition/body-1b01t
crawled: 2025-12-03T06:18:39Z
---

# body

**Instance Property**

The constraints of the formatting definition.

## Declaration

```swift
@AttributedTextFormatting.DefinitionBuilder<Self.Scope> var body: Self.Body { get }
```

## Discussion

When you implement a custom definition, you must implement a computed `body` property to provide the constraints of your definition. Return a definition that’s composed of built-in definitions that SwiftUI provides, such as [ValueConstraint](ValueConstraint.zh-Hans.md) and [AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md)s, plus other composite [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md)s that you’ve already defined:

```swift
struct MyTextFormattingDefinition: AttributedTextFormattingDefinition {
    var body: some AttributedTextFormattingDefinition<
        AttributeScopes.SwiftUIAttributes
    > {
        ValueConstraint(
            for: \.underlineStyle,
            values: [nil, .single],
            default: .single)
        MyAttributedTextValueConstraint()
    }
}
```

Note that the order of the constraints in the result builder matters as constraints are applied in order. For details, see `AttributedTextValueConstraint/constrain(_:)-(Attributes)`.

