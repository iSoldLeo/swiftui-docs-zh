---
来源：https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/ValueConstraint/init(for:values:default:)
抓取时间： 2025-12-04T13:19:55Z
---

# init(for:values:default:)

**Initializer**

创建一个定义，将属性值限制在一组已定义的允许值范围内。

### 声明

```swift
init(for attribute: AttributeKey.Type, values allowedValues: Set<AttributeKey.Value?>, default defaultValue: AttributeKey.Value?)
```

## 参数

- **allowedValues**：一组允许使用的值。
- **defaultValue**：单个允许值，用于替换不在`allowedValues` 中的任何值。


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/ValueConstraint/init(for:values:default:)
crawled: 2025-12-04T13:19:55Z
---

# init(for:values:default:)

**Initializer**

Create a definition that constrains an attribute’s value to a defined set of allowed values.

## Declaration

```swift
init(for attribute: AttributeKey.Type, values allowedValues: Set<AttributeKey.Value?>, default defaultValue: AttributeKey.Value?)
```

## Parameters

- **allowedValues**: A set of values that are permitted.
- **defaultValue**: A single permitted value that is used to replace any values that are not in the set of `allowedValues`.

