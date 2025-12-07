---
来源： https://developer.apple.com/documentation/swiftui/attributedtextformattingdefinition
抓取时间： 2025-12-05T22:23:33Z
---

# 属性文本格式定义

**Protocol**

用于定义视图中文本样式的协议。

## 声明

```swift
protocol AttributedTextFormattingDefinition<Scope>
```

## 概览

格式化定义由一个属性范围和若干值约束组成。当使用[doc://com.apple.SwiftUI/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)-81jn6] 视图修饰符初始化[Text](Text.zh-Hans.md) 和[TextEditor](TextEditor.zh-Hans.md) 视图时，格式化定义会影响嵌套的[Text](Text.zh-Hans.md) 和[TextEditor](TextEditor.zh-Hans.md) 视图。

创建格式化定义时，首先要选择一个属性范围，其中包含与视图相关的所有属性。值约束和受影响的视图将忽略所有其他属性。

使用 `Foundation/AttributeScopes/SwiftUIAttributes` 查看 SwiftUI 支持的默认属性集。您可以创建自己的作用域，但只列出 SwiftUI 属性作用域中的属性子集。您还可以在作用域中包含自定义属性。这样，您就可以利用高级属性字符串功能，如 [doc://com.apple.documentation/documentation/Foundation/AttributedStringKey/runBoundaries]。

自定义属性还可以将存储在文本中的语义信息（例如，某个字符序列指代联系人中的某个特定人员）与如何格式化这部分文本（例如，前景色为 "紫色"）区分开来。定义属性值的规则称为[AttributedTextValueConstraint](AttributedTextValueConstraint.zh-Hans.md)。

```swift
struct ContactsArePurple: AttributedTextValueConstraint {
    typealias Scope = MyScope
    typealias AttributeKey = Scope.ForegroundColorAttribute

    func constrain(_ container: inout Attributes) {
        if container.annotation == .contact {
            container.foregroundColor = .purple
        } else {
            container.foregroundColor = nil
        }
    }
}
```

将格式与自定义语义属性关联起来是一个重要用例，而值约束则是一种通用机制，用于约束文本编辑器中可用的格式--无论是否依赖于其他属性。例如，值约束也可用于只允许使用单实线下划线，而不允许使用双下划线或虚线下划线。

SwiftUI 会验证系统提供给用户的格式化用户界面，以确保只有与格式化定义及其约束兼容的控件才可见并启用。如果系统格式化用户界面不能根据您的格式化定义提供足够的实用性，或者您提供的自定义用户界面更适合您的文本编辑体验，请考虑使用[textInputFormattingControlVisibility(_:for:)](View/textInputFormattingControlVisibility___for.zh-Hans.md)视图修饰符隐藏系统提供的用户界面。

要声明归属文本格式定义，请在[body-1b01t](AttributedTextFormattingDefinition/body-1b01t.zh-Hans.md) 类型的泛型中指定属性范围，并使用结果生成器语法在[body-1b01t](AttributedTextFormattingDefinition/body-1b01t.zh-Hans.md) 中列出所有值约束：

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
        ContactsArePurple()
    }
}
```

使用[doc://com.apple.SwiftUI/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)-81jn6] 视图修饰符将定义应用于视图。

### 关联类型

- **Body**：代表此格式化定义主体的视图类型。
- **Scope**：文本格式定义只允许使用此属性范围中的属性。

### 实例属性

- **body**：格式化定义的约束条件。

### 实例方法

- **constrain(_:)**：将所有值约束应用于给定的属性容器。

### 类型别名

- **AttributedTextFormattingDefinition.ValueConstraint**：文本格式定义，允许使用单个属性，可选择限制为一组值。

## 控制文本样式

- **bold(_:)**：为该视图中的文本应用粗体字体权重。
- **italic(_:)**：为该视图中的文本应用斜体。
- **underline(_:pattern:color:)**：为该视图中的文本应用下划线。
- **strikethrough(_:pattern:color:)**：为该视图中的文本应用删除线。
- **textCase(_:)**：为该视图中包含的文本在显示时的大小写设置变换。
- **textCase**：样式覆盖，用于在显示`Text` 时使用环境的本地语言转换大小写。
- **monospaced(_:)**：尽可能修改所有子视图的字体，使其使用当前字体的固定宽度变体。
- **monospacedDigit()**：修改所有子视图的字体，尽可能使用固定宽度的数字，同时按比例保留其他字符的间距。
- **AttributedTextValueConstraint**：用于定义对某一属性值的约束的协议。
- **AttributedTextFormatting**：与归属文本格式定义相关的类型命名空间。

## 继承自

- 属性文本值约束

## 符合类型

- AttributedTextFormatting.AnyDefinition
- AttributedTextFormatting.EmptyDefinition（空定义
- 属性文本格式.元组定义
- AttributedTextFormatting.ValueConstraint（值约束


---
source: https://developer.apple.com/documentation/swiftui/attributedtextformattingdefinition
crawled: 2025-12-05T22:23:33Z
---

# AttributedTextFormattingDefinition

**Protocol**

A protocol for defining how text can be styled in a view.

## Declaration

```swift
protocol AttributedTextFormattingDefinition<Scope>
```

## Overview

A formatting definition consists of an attribute scope and a number of value constraints. It is applied to a view hierarchy using the [doc://com.apple.SwiftUI/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)-81jn6] view modifier and affects nested [Text](Text.zh-Hans.md) and [TextEditor](TextEditor.zh-Hans.md) views when initialized with [doc://com.apple.documentation/documentation/Foundation/AttributedString].

Create a formatting definition by first choosing an attribute scope that contains all attributes relevant for your view. All other attributes will be ignored by value constraints and by the affected views.

Use the `Foundation/AttributeScopes/SwiftUIAttributes` for the default set of attributes supported by SwiftUI. You can create your own scope only listing out a subset of the attributes in SwiftUI’s attribute scope. You can also include custom attributes in your scope. This allows you to take advantage of advanced attributed string features, such as [doc://com.apple.documentation/documentation/Foundation/AttributedStringKey/runBoundaries].

Custom attributes also allow you to separate semantic information stored on the text, e.g. the information that a sequence of characters refers a specific person in contacts, from how this part of the text is to be formatted, e.g. with the foreground color “purple”. The rules defining what values attributes can have, are called [AttributedTextValueConstraint](AttributedTextValueConstraint.zh-Hans.md)s.

```swift
struct ContactsArePurple: AttributedTextValueConstraint {
    typealias Scope = MyScope
    typealias AttributeKey = Scope.ForegroundColorAttribute

    func constrain(_ container: inout Attributes) {
        if container.annotation == .contact {
            container.foregroundColor = .purple
        } else {
            container.foregroundColor = nil
        }
    }
}
```

While associating formatting with custom semantic attributes is one important use case, value constraints are a generic mechanism for constraining the formatting that is available in a text editor - with or without dependencies on other attributes. For example, a value constraint could also be used to only allow a single, solid underline, but not a double underline or a dashed underline.

SwiftUI validates formatting UI provided by the system to the user to make sure only controls that are compatible with your formatting definition and its constraints are visible and enabled. If the system formatting UI does not provide sufficient utility based on your formatting definition, or you provide custom UI that is better tailored to your text editing experience, consider hiding the system-provided UI using the [textInputFormattingControlVisibility(_:for:)](View/textInputFormattingControlVisibility___for.zh-Hans.md) view modifier.

To declare the attributed text formatting definition, specify the attribute scope in the generic of the [body-1b01t](AttributedTextFormattingDefinition/body-1b01t.zh-Hans.md)’s type, and list all value constraints inside the [body-1b01t](AttributedTextFormattingDefinition/body-1b01t.zh-Hans.md) using result builder syntax:

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
        ContactsArePurple()
    }
}
```

Use the [doc://com.apple.SwiftUI/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)-81jn6] view modifier to apply the definition to a view.

## Associated Types

- **Body**: The type of view representing the body of this formatting definition.
- **Scope**: The text formatting definition only allows usage of attributes in this attribute scope.

## Instance Properties

- **body**: The constraints of the formatting definition.

## Instance Methods

- **constrain(_:)**: Applies all value constraints to a given attribute container.

## Type Aliases

- **AttributedTextFormattingDefinition.ValueConstraint**: A text formatting definition that permits a single attribute to be used, optionally constrained to a set of values.

## Controlling text style

- **bold(_:)**: Applies a bold font weight to the text in this view.
- **italic(_:)**: Applies italics to the text in this view.
- **underline(_:pattern:color:)**: Applies an underline to the text in this view.
- **strikethrough(_:pattern:color:)**: Applies a strikethrough to the text in this view.
- **textCase(_:)**: Sets a transform for the case of the text contained in this view when displayed.
- **textCase**: A stylistic override to transform the case of `Text` when displayed, using the environment’s locale.
- **monospaced(_:)**: Modifies the fonts of all child views to use the fixed-width variant of the current font, if possible.
- **monospacedDigit()**: Modifies the fonts of all child views to use fixed-width digits, if possible, while leaving other characters proportionally spaced.
- **AttributedTextValueConstraint**: A protocol for defining a constraint on the value of a certain attribute.
- **AttributedTextFormatting**: A namespace for types related to attributed text formatting definitions.

## Inherited By

- AttributedTextValueConstraint

## Conforming Types

- AttributedTextFormatting.AnyDefinition
- AttributedTextFormatting.EmptyDefinition
- AttributedTextFormatting.TupleDefinition
- AttributedTextFormatting.ValueConstraint

