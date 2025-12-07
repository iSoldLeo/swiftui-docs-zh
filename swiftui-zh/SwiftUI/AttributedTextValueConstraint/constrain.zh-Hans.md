--- 来源：https://developer.apple.com/documentation/SwiftUI/AttributedTextValueConstraint/constrain(_:)

抓取时间：2025-12-03T06:18:44Z

---

# constrain(_:)

**实例方法**

强制属性的约束。

## 声明

```swift
func constrain(_ container: inout Self.Attributes)
```

## 讨论

此函数转换给定 `container` 上的 [AttributeKey](AttributeKey.zh-Hans.md)，使其表示符合规范的类型定义的有效格式。

此函数通常可以读取 `container` 上的任何属性，并生成一个受上方关联文本格式定义中列出的所有 [AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md) 约束的值。

请考虑以下示例：

```swift
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

当此约束函数访问 `container.foregroundColor` 时，系统会确定背景色取决于前景色。此时，系统会检查此约束所属的 [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) 是否定义了位于 `NoEqualForegroundAndBackground` 上方的前景色约束，并应用这些约束。因此，当访问 `container.foregroundColor` 返回时，此函数会读取约束值。


---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextValueConstraint/constrain(_:)
crawled: 2025-12-03T06:18:44Z
---

# constrain(_:)

**Instance Method**

Enforce constraints on the attribute.

## Declaration

```swift
func constrain(_ container: inout Self.Attributes)
```

## Discussion

A function that transforms the [AttributeKey](AttributeKey.zh-Hans.md) on the given `container` so it represents a formatting that the conforming type defines to be valid.

This function can generally read any attribute on `container` and it will produce a value that has been constrained by all [AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md) listed in the associated text formatting definition above the constraint reading the attribute.

Consider the following example:

```swift
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

When this constrain function accesses `container.foregroundColor`, the system establishes that the background color depends on the foreground color. At that time, it checks if the [AttributedTextFormattingDefinition](../AttributedTextFormattingDefinition.zh-Hans.md) this constraint is part of defines constraints on the foreground color *above* `NoEqualForegroundAndBackground` and applies them. Thus, when the access to `container.foregroundColor` returns, this function reads the constrained value.

