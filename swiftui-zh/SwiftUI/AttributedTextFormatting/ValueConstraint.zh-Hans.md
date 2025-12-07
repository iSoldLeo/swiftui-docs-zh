---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/ValueConstraint
抓取时间： 2025-12-03T06:18:43Z
---

# AttributedTextFormatting.ValueConstraint

**Structure**

文本格式定义，用于将单个属性的值限制为集合的成员。

### 声明

```swift
struct ValueConstraint<Scope, AttributeKey> where Scope : AttributeScope, AttributeKey : AttributedStringKey, AttributeKey.Value : Sendable
```

## 概览

```swift
struct MyTextFormattingDefinition: AttributedTextFormattingDefinition {
    var body: some AttributedTextFormattingDefinition<
        AttributeScopes.SwiftUIAttributes
    > {
        // Allow no underline or the `.single` underline style. If
        // a text has any other underline style, it is corrected
        // to the default value `.single`
        ValueConstraint(
            for: \.underlineStyle,
            values: [nil, .single],
            default: .single)
    }
}
```

## 初始化程序

- **init(for:values:default:)**：创建一个定义，将属性值限制在一组已定义的允许值范围内。

## 符合

- 属性文本格式定义
- 属性文本值约束
- 等价
- 可散列
- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/ValueConstraint
crawled: 2025-12-03T06:18:43Z
---

# AttributedTextFormatting.ValueConstraint

**Structure**

A text formatting definition that constrains the value of a single attribute to the members of a set.

## Declaration

```swift
struct ValueConstraint<Scope, AttributeKey> where Scope : AttributeScope, AttributeKey : AttributedStringKey, AttributeKey.Value : Sendable
```

## Overview

```swift
struct MyTextFormattingDefinition: AttributedTextFormattingDefinition {
    var body: some AttributedTextFormattingDefinition<
        AttributeScopes.SwiftUIAttributes
    > {
        // Allow no underline or the `.single` underline style. If
        // a text has any other underline style, it is corrected
        // to the default value `.single`
        ValueConstraint(
            for: \.underlineStyle,
            values: [nil, .single],
            default: .single)
    }
}
```

## Initializers

- **init(for:values:default:)**: Create a definition that constrains an attribute’s value to a defined set of allowed values.

## Conforms To

- AttributedTextFormattingDefinition
- AttributedTextValueConstraint
- Equatable
- Hashable
- Sendable
- SendableMetatype

