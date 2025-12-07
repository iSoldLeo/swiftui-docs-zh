---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/AttributeContainerProxy
抓取时间： 2025-12-03T06:18:46Z
---

# AttributedTextFormatting.AttributeContainerProxy

**Structure**

部分已验证属性集的代理。

## 声明

```swift
@dynamicMemberLookup struct AttributeContainerProxy<Scope, Attribute> where Scope : AttributeScope, Attribute : AttributedStringKey, Attribute.Value : Sendable
```

## 概览

将`Attribute`公开为读写属性，将所有其他属性公开为只读属性。该类型会自动查询底层的 [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) 以限制访问的值。

### 结构

- **AttributedTextFormatting.AttributeContainerProxy.Scoped**：部分已验证属性集的作用域代理。

## 下标

- **subscript(_:)**：访问要限制的属性值。
- **subscript(dynamicMember:)**：访问要约束的属性值。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/AttributeContainerProxy
crawled: 2025-12-03T06:18:46Z
---

# AttributedTextFormatting.AttributeContainerProxy

**Structure**

A proxy for a partially validated set of attributes.

## Declaration

```swift
@dynamicMemberLookup struct AttributeContainerProxy<Scope, Attribute> where Scope : AttributeScope, Attribute : AttributedStringKey, Attribute.Value : Sendable
```

## Overview

Exposes `Attribute` as read-write and all other attributes as read-only. The type automatically queries the underlying [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) to constrain values that are accessed.

## Structures

- **AttributedTextFormatting.AttributeContainerProxy.Scoped**: A scoped proxy for a partially validated set of attributes.

## Subscripts

- **subscript(_:)**: Access the value of the attribute to constrain.
- **subscript(dynamicMember:)**: Access the value of the attribute to constrain.

## Conforms To

- Sendable
- SendableMetatype

