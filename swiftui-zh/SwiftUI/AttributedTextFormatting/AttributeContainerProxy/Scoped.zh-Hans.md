---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/AttributeContainerProxy/Scoped
抓取时间： 2025-12-04T13:19:56Z
---

# AttributedTextFormatting.AttributeContainerProxy.Scoped

**Structure**

部分已验证属性集的作用域代理。

### 声明

```swift
@dynamicMemberLookup struct Scoped<Subscope> where Subscope : AttributeScope
```

## 概览

将`Attribute`公开为读写属性，将作用域中的所有其他属性公开为只读属性。该类型会自动查询底层的 [AttributedTextFormattingDefinition](../../AttributedTextFormattingDefinition.zh-Hans.md) 以限制被访问的值。



### 下标

- **subscript(dynamicMember:)**：访问要限制的属性值。

## 符合

- 可发送
- 可发送元类型


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/AttributeContainerProxy/Scoped
crawled: 2025-12-04T13:19:56Z
---

# AttributedTextFormatting.AttributeContainerProxy.Scoped

**Structure**

A scoped proxy for a partially validated set of attributes.

## Declaration

```swift
@dynamicMemberLookup struct Scoped<Subscope> where Subscope : AttributeScope
```

## Overview

Exposes `Attribute` as read-write and all other attributes in the scope as read-only. The type automatically queries the underlying [AttributedTextFormattingDefinition](../../AttributedTextFormattingDefinition.zh-Hans.md) to constrain values that are accessed.



## Subscripts

- **subscript(dynamicMember:)**: Access the value of the attribute to constrain.

## Conforms To

- Sendable
- SendableMetatype

