---
来源： https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey
抓取时间： 2025-12-02T17:35:42Z
---

# 本地化字符串关键字

**Structure**

用于在字符串文件或字符串字典文件中查找条目的键。

## 声明

```swift
@frozen struct LocalizedStringKey
```

## 概览

一些 SwiftUI 类型（如 [Text](Text.zh-Hans.md)、[Toggle](Toggle.zh-Hans.md)、[Picker](Picker.zh-Hans.md) 和其他类型）的初始化器会在您提供字符串字面量时隐式地查找本地化字符串。当您使用初始化器 `Text("Hello")` 时，SwiftUI 会为您创建一个 `LocalizedStringKey`，并使用它查找 `Hello` 字符串的本地化。这是因为 `LocalizedStringKey` 符合 [doc://com.apple.documentation/documentation/Swift/ExpressibleByStringLiteral]。

初始化器接受`LocalizedStringKey`的类型通常都有一个相应的初始化器，该初始化器接受一个符合[doc://com.apple.documentation/documentation/Swift/StringProtocol]的参数。将`String` 变量传递给这些初始化器可以避免本地化，这在变量包含用户提供的值时通常是合适的。

一般来说，需要本地化时使用字符串字面参数，不需要时使用字符串变量参数。如果要本地化字符串变量的值，则使用字符串创建一个新的`LocalizedStringKey` 实例。

下面的示例展示了如何创建带本地化和不带本地化的[Text](Text.zh-Hans.md) 实例。提供给 [Section](Section.zh-Hans.md) 的标题参数是一个字面字符串，因此 SwiftUI 为其创建了一个 `LocalizedStringKey`。但是，`messageStore.today` 数组中的字符串项是`String` 变量，因此列表中的[Text](Text.zh-Hans.md) 视图会逐字使用字符串值。

```swift
List {
    Section(header: Text("Today")) {
        ForEach(messageStore.today) { message in
            Text(message.title)
        }
    }
}
```

如果应用程序已本地化为日文，其`Localizable.strings` 文件的翻译如下：

```other
"Today" = "今日";
```

在日语中运行时，该示例会生成如下列表，将 "Today "部分的标题本地化，但不会本地化列表项。



## 从字面值创建键

- **init(_:)**：从给定的字符串值创建本地化字符串键。
- **init(stringLiteral:)**：从给定的字符串字面量创建本地化字符串键。

## 从插值创建键

- **init(stringInterpolation:)**：从给定的字符串插值创建本地化字符串键。
- **LocalizedStringKey.StringInterpolation**：在创建字符串字面量时，用插值表示字符串字面量的内容，用于创建本地化字符串键。

## 本地化文本

- 为本地化准备视图**：指定提示并添加字符串以本地化 SwiftUI 视图。
- **locale**：视图应使用的当前语言。
- **typesettingLanguage(_:isEnabled:)**：指定排版语言。
- **TypesettingLanguage**：定义如何确定文本的排版语言。

## 符合

- 等价
- ExpressibleByExtendedGraphemeClusterLiteral（可通过扩展音节集表达
- 可通过字符串插值表达
- 可通过字符串字头表达
- 可通过 UnicodeScalarLiteral 表达


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey
crawled: 2025-12-02T17:35:42Z
---

# LocalizedStringKey

**Structure**

The key used to look up an entry in a strings file or strings dictionary file.

## Declaration

```swift
@frozen struct LocalizedStringKey
```

## Overview

Initializers for several SwiftUI types – such as [Text](Text.zh-Hans.md), [Toggle](Toggle.zh-Hans.md), [Picker](Picker.zh-Hans.md) and others –  implicitly look up a localized string when you provide a string literal. When you use the initializer `Text("Hello")`, SwiftUI creates a `LocalizedStringKey` for you and uses that to look up a localization of the `Hello` string. This works because `LocalizedStringKey` conforms to [doc://com.apple.documentation/documentation/Swift/ExpressibleByStringLiteral].

Types whose initializers take a `LocalizedStringKey` usually have a corresponding initializer that accepts a parameter that conforms to [doc://com.apple.documentation/documentation/Swift/StringProtocol]. Passing a `String` variable to these initializers avoids localization, which is usually appropriate when the variable contains a user-provided value.

As a general rule, use a string literal argument when you want localization, and a string variable argument when you don’t. In the case where you want to localize the value of a string variable, use the string to create a new `LocalizedStringKey` instance.

The following example shows how to create [Text](Text.zh-Hans.md) instances both with and without localization. The title parameter provided to the [Section](Section.zh-Hans.md) is a literal string, so SwiftUI creates a `LocalizedStringKey` for it. However, the string entries in the `messageStore.today` array are `String` variables, so the [Text](Text.zh-Hans.md) views in the list use the string values verbatim.

```swift
List {
    Section(header: Text("Today")) {
        ForEach(messageStore.today) { message in
            Text(message.title)
        }
    }
}
```

If the app is localized into Japanese with the following translation of its `Localizable.strings` file:

```other
"Today" = "今日";
```

When run in Japanese, the example produces a list like the following, localizing “Today” for the section header, but not the list items.



## Creating a key from a literal value

- **init(_:)**: Creates a localized string key from the given string value.
- **init(stringLiteral:)**: Creates a localized string key from the given string literal.

## Creating a key from an interpolation

- **init(stringInterpolation:)**: Creates a localized string key from the given string interpolation.
- **LocalizedStringKey.StringInterpolation**: Represents the contents of a string literal with interpolations while it’s being built, for use in creating a localized string key.

## Localizing text

- **Preparing views for localization**: Specify hints and add strings to localize your SwiftUI views.
- **locale**: The current locale that views should use.
- **typesettingLanguage(_:isEnabled:)**: Specifies the language for typesetting.
- **TypesettingLanguage**: Defines how typesetting language is determined for text.

## Conforms To

- Equatable
- ExpressibleByExtendedGraphemeClusterLiteral
- ExpressibleByStringInterpolation
- ExpressibleByStringLiteral
- ExpressibleByUnicodeScalarLiteral

