---
来源： https://developer.apple.com/documentation/SwiftUI/AttributedTextFormattingDefinition/constrain(_:)
抓取时间： 2025-12-01T11:07:49Z
---

# constrain(_:)

**实例方法**

将所有值约束应用于给定的属性容器。

## 声明

```swift
func constrain(_ container: inout AttributeContainer)
```

## 讨论

通过将属于此定义一部分的所有[AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md) 应用于容器来修改给定的`container`。

使用该函数可以测试您的[AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md)，或者在将内容传递给本身无法应用该定义的 API 之前确保应用了您的约束。


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormattingDefinition/constrain(_:)
crawled: 2025-12-01T11:07:49Z
---

# constrain(_:)

**Instance Method**

Applies all value constraints to a given attribute container.

## Declaration

```swift
func constrain(_ container: inout AttributeContainer)
```

## Discussion

Modifies the given `container` by applying all [AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md)s that are part of this definition to the container.

Use this function to test your [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md), or to ensure your constraints are applied before passing content to API that cannot itself apply the definition.

