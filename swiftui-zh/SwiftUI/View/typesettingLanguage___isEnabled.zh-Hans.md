--- 来源：https://developer.apple.com/documentation/SwiftUI/View/typesettingLanguage(_:isEnabled:)

抓取时间：2025-12-02T17:35:43Z

---

# typesettingLanguage(_:isEnabled:)

**实例方法**

指定排版语言。

## 声明

```swift
nonisolated func typesettingLanguage(_ language: Locale.Language, isEnabled: Bool = true) -> some View

```

## 参数

- **language**：用于排版的显式语言。

- **isEnabled**：一个布尔值，指示是否添加文本语言。

## 返回值

一个视图，其排版语言设置为您提供的值。

## 说明

在某些情况下，`Text` 可能包含与设备 UI 语言不匹配的特定语言的文本。在这种情况下，指定一种语言很有用，这样行高、换行和间距就会遵循该语言使用的脚本。例如：

```swift
Text(verbatim: "แอปเปิล")
    .typesettingLanguage(.init(languageCode: .thai))
```

注意：此语言不会影响文本本地化。

## 文本本地化

- **准备视图进行本地化**：指定提示并添加字符串以本地化您的 SwiftUI 视图。

- **LocalizedStringKey**：用于在字符串文件或字符串字典文件中查找条目的键。

- **locale**：视图应使用的当前区域设置。

- **TypesettingLanguage**：定义如何确定文本的排版语言。


---
source: https://developer.apple.com/documentation/SwiftUI/View/typesettingLanguage(_:isEnabled:)
crawled: 2025-12-02T17:35:43Z
---

# typesettingLanguage(_:isEnabled:)

**Instance Method**

Specifies the language for typesetting.

## Declaration

```swift
nonisolated func typesettingLanguage(_ language: Locale.Language, isEnabled: Bool = true) -> some View

```

## Parameters

- **language**: The explicit language to use for typesetting.
- **isEnabled**: A Boolean value that indicates whether text language is added

## Return Value

A view with the typesetting language set to the value you supply.

## Discussion

In some cases `Text` may contain text of a particular language which doesn’t match the device UI language. In that case it’s useful to specify a language so line height, line breaking and spacing will respect the script used for that language. For example:

```swift
Text(verbatim: "แอปเปิล")
    .typesettingLanguage(.init(languageCode: .thai))
```

Note: this language does not affect text localization.

## Localizing text

- **Preparing views for localization**: Specify hints and add strings to localize your SwiftUI views.
- **LocalizedStringKey**: The key used to look up an entry in a strings file or strings dictionary file.
- **locale**: The current locale that views should use.
- **TypesettingLanguage**: Defines how typesetting language is determined for text.

