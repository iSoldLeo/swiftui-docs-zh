--- 来源：https://developer.apple.com/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)

抓取时间：2025-11-30T21:07:37Z

---

# attributedTextFormattingDefinition(_:)

**实例方法**

将文本格式定义应用于嵌套视图。

## 声明

```swift
nonisolated func attributedTextFormattingDefinition<D>(_ definition: D) -> some View where D : AttributedTextFormattingDefinition

```

## 讨论

将文本格式定义应用于分别使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-1a4oh] 或 [init(text:selection:)](../TextEditor/init_text_selection.zh-Hans.md) 初始化器创建的 [Text](../Text.zh-Hans.md) 或 [TextEditor](../TextEditor.zh-Hans.md)，可确保用户可观察到的所有内容都符合格式定义的约束。

您可以根据属性范围和一系列 [AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md) 来创建自己的定义：

```swift
// MyTextFormattingDefinition.swift

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

// MyEditorView.swift

TextEditor(text: $text)
    .attributedTextFormattingDefinition(MyTextFormattingDefinition())
```

要手动强制执行约束（例如，在序列化文本内容之前），请使用 [doc://com.apple.SwiftUI/documentation/SwiftUI/AttributedTextFormattingDefinition/constrain(_:)-1ur9c] 方法。


---
source: https://developer.apple.com/documentation/SwiftUI/View/attributedTextFormattingDefinition(_:)
crawled: 2025-11-30T21:07:37Z
---

# attributedTextFormattingDefinition(_:)

**Instance Method**

Apply a text formatting definition to nested views.

## Declaration

```swift
nonisolated func attributedTextFormattingDefinition<D>(_ definition: D) -> some View where D : AttributedTextFormattingDefinition

```

## Discussion

Applying a text formatting definition to a [Text](../Text.zh-Hans.md) or [TextEditor](../TextEditor.zh-Hans.md) created using the [doc://com.apple.SwiftUI/documentation/SwiftUI/Text/init(_:)-1a4oh] or [init(text:selection:)](../TextEditor/init_text_selection.zh-Hans.md) initializer, respectively, makes sure that any content observable to the user adheres to the constraints of the formatting definition.

You can compose your own definition from an attribute scope and a series of [AttributedTextValueConstraint](../AttributedTextValueConstraint.zh-Hans.md)s:

```swift
// MyTextFormattingDefinition.swift

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

// MyEditorView.swift

TextEditor(text: $text)
    .attributedTextFormattingDefinition(MyTextFormattingDefinition())
```



To manually enforce constraints, e.g. before serializing text contents, use the [doc://com.apple.SwiftUI/documentation/SwiftUI/AttributedTextFormattingDefinition/constrain(_:)-1ur9c] method.

