--- 来源：https://developer.apple.com/documentation/swiftui/contentsizecategory

抓取时间：2025-12-04T13:21:54Z

---

# ContentSizeCategory

**Enumeration**

您可以为内容指定尺寸。

＃＃ 宣言

```swift
enum ContentSizeCategory
```

## 内容大小类别

- **ContentSizeCategory.accessibilityExtraExtraExtraLarge**
- **ContentSizeCategory.accessibilityExtraExtraLarge**
- **ContentSizeCategory.accessibilityExtraLarge**
- **ContentSizeCategory.accessibilityLarge**
- **ContentSizeCategory.accessibilityMedium**
- **ContentSizeCategory.extraExtraExtraLarge**
- **ContentSizeCategory.extraExtraLarge**
- **ContentSizeCategory.extraLarge**
- **ContentSizeCategory.extraSmall**
- **ContentSizeCategory.large**
- **ContentSizeCategory.medium**
- **ContentSizeCategory.small**

## 创建尺寸类别

- **init(_:)**：从 UIContentSizeCategory 等效项创建尺寸类别。

## 比较内容大小类别

- **isAccessibilityCategory**：返回一个布尔值，指示内容大小类别是否与辅助功能相关。

## 运算符

- **<(_:_:)**：返回一个布尔值，指示第一个参数的值是否小于第二个参数的值。

- **>(_:_:)**：返回一个布尔值，指示第一个参数的值是否大于第二个参数的值。

- **<=(_:_:)**：返回一个布尔值，指示第一个参数的值是否小于或等于第二个参数的值。

- **>=(_:_:)**：返回一个布尔值，指示第一个参数的值是否大于或等于第二个参数的值。

## 符合以下标准

- CaseIterable

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/swiftui/contentsizecategory
crawled: 2025-12-04T13:21:54Z
---

# ContentSizeCategory

**Enumeration**

The sizes that you can specify for content.

## Declaration

```swift
enum ContentSizeCategory
```

## Content size categories

- **ContentSizeCategory.accessibilityExtraExtraExtraLarge**
- **ContentSizeCategory.accessibilityExtraExtraLarge**
- **ContentSizeCategory.accessibilityExtraLarge**
- **ContentSizeCategory.accessibilityLarge**
- **ContentSizeCategory.accessibilityMedium**
- **ContentSizeCategory.extraExtraExtraLarge**
- **ContentSizeCategory.extraExtraLarge**
- **ContentSizeCategory.extraLarge**
- **ContentSizeCategory.extraSmall**
- **ContentSizeCategory.large**
- **ContentSizeCategory.medium**
- **ContentSizeCategory.small**

## Creating a size category

- **init(_:)**: Create a size category from its UIContentSizeCategory equivalent.

## Comparing content size categories

- **isAccessibilityCategory**: A Boolean value indicating whether the content size category is one that is associated with accessibility.

## Operators

- **<(_:_:)**: Returns a Boolean value indicating whether the value of the first argument is less than that of the second argument.
- **>(_:_:)**: Returns a Boolean value indicating whether the value of the first argument is greater than that of the second argument.
- **<=(_:_:)**: Returns a Boolean value indicating whether the value of the first argument is less than or equal to that of the second argument.
- **>=(_:_:)**: Returns a Boolean value indicating whether the value of the first argument is greater than or equal to that of the second argument.

## Conforms To

- CaseIterable
- Equatable
- Hashable
- Sendable
- SendableMetatype

