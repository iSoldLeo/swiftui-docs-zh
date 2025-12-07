--- 来源：https://developer.apple.com/documentation/SwiftUI/View/autocapitalization(_:)

抓取时间：2025-12-01T10:24:39Z

---

# autocapitalization(_:)

**实例方法**

设置是否对此视图应用自动首字母大写。

## 声明

```swift
nonisolated func autocapitalization(_ style: UITextAutocapitalizationType) -> some View

```

## 参数

- **style**：枚举 [doc://com.apple.documentation/documentation/UIKit/UITextAutocapitalizationType] 中定义的自动首字母大写模式之一。

## 说明

当需要自动将单词、句子或其他文本（例如专有名词）的首字母大写时，请使用此方法。

在以下示例中，用户输入文本时，每个单词都会自动首字母大写：

```swift
TextField("Last, First", text: $fullName)
    .autocapitalization(UITextAutocapitalizationType.words)
```

[doc://com.apple.documentation/documentation/UIKit/UITextAutocapitalizationType] 枚举定义了可用的首字母大写模式。默认值为 [doc://com.apple.documentation/documentation/UIKit/UITextAutocapitalizationType/sentences]。

## 文本修饰符

- **disableAutocorrection(_:)**：设置是否禁用此视图的自动纠错功能。


---
source: https://developer.apple.com/documentation/SwiftUI/View/autocapitalization(_:)
crawled: 2025-12-01T10:24:39Z
---

# autocapitalization(_:)

**Instance Method**

Sets whether to apply auto-capitalization to this view.

## Declaration

```swift
nonisolated func autocapitalization(_ style: UITextAutocapitalizationType) -> some View

```

## Parameters

- **style**: One of the autocapitalization modes defined in the [doc://com.apple.documentation/documentation/UIKit/UITextAutocapitalizationType] enumeration.

## Discussion

Use this method when you need to automatically capitalize words, sentences, or other text like proper nouns.

In example below, as the user enters text each word is automatically capitalized:

```swift
TextField("Last, First", text: $fullName)
    .autocapitalization(UITextAutocapitalizationType.words)
```

The [doc://com.apple.documentation/documentation/UIKit/UITextAutocapitalizationType] enumeration defines the available capitalization modes. The default is [doc://com.apple.documentation/documentation/UIKit/UITextAutocapitalizationType/sentences].

## Text modifiers

- **disableAutocorrection(_:)**: Sets whether to disable autocorrection for this view.

