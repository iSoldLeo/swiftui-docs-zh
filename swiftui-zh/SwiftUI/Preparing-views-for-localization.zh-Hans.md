--- 来源：https://developer.apple.com/documentation/SwiftUI/Preparing-views-for-localization

抓取时间：2025-12-02T16:10:42Z

---

# 为本地化准备视图

**Article**

指定提示并添加字符串以本地化您的 SwiftUI 视图。

## 概述

本地化 SwiftUI 视图，让用户能够以他们自己的母语、地区和文化体验您的应用。导出本地化目录时，Xcode 会解析 SwiftUI 视图以查找要本地化的字符串。您可以添加提示，以便 Xcode 为您的应用生成正确的、带有提示的本地化字符串。

有关字符串目录的信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/localizing-and-varying-text-with-a-string-catalog]。

### 为文本视图添加注释

为了简化翻译过程，您可以向译者提供提示，说明您的应用如何以及在何处显示 [Text](Text.zh-Hans.md) 视图中的字符串。要添加提示，请使用文本视图初始化器 [init(_:tableName:bundle:comment:)](Text/init___tableName_bundle_comment.zh-Hans.md) 的可选参数 `comment`。当您使用 Xcode 本地化应用时，它会将注释字符串与文本视图一起包含。例如，以下文本视图包含一条注释：

```swift
Text("Explore",
     comment: "The title of the tab bar item that navigates to the Explore screen.")
```

Xcode 会为该视图在字符串目录文件中创建以下条目：

### 为文本视图提供附加信息

您可以通过提供一个 SwiftUI 会解释为 [LocalizedStringKey](LocalizedStringKey.zh-Hans.md) 的字符串，来本地化许多带有字符串标签的 SwiftUI 视图。系统会在运行时使用此键从字符串目录中检索本地化值，如果找不到该键，则直接使用该字符串。例如，SwiftUI 使用以下 [Label](Label.zh-Hans.md) 初始化器的字符串输入作为本地化字符串键：

```swift
Label("Message", image: "msgSymbol")
```

如果您还想为本地化添加注释，可以使用显式的 [Text](Text.zh-Hans.md) 视图：

```swift
Label {
    Text("Message",
         comment: "A label that displays 'Message' and a corresponding image.")
} icon: {
    Image("msgSymbol")
}
```

许多 SwiftUI 控件都具有视图构建器初始化器，使您能够遵循此模式。有关如何使应用程序的文本可翻译的更多信息，请参阅 [doc://com.apple.documentation/documentation/Xcode/preparing-your-apps-text-for-translation]。

## 文本本地化

- **LocalizedStringKey**：用于在字符串文件或字符串字典文件中查找条目的键。

- **locale**：视图应使用的当前区域设置。

- **typesettingLanguage(_:isEnabled:)**：指定排版语言。 - **TypesettingLanguage**：定义文本的排版语言确定方式。


---
source: https://developer.apple.com/documentation/SwiftUI/Preparing-views-for-localization
crawled: 2025-12-02T16:10:42Z
---

# Preparing views for localization

**Article**

Specify hints and add strings to localize your SwiftUI views.

## Overview

Localize SwiftUI views so users experience your app in their own native language, region, and culture. Xcode parses SwiftUI views for strings to localize when exporting a localization catalog. You can add hints so that Xcode generates correct, hinted strings to localize for your app.

For information about string catalogs, see [doc://com.apple.documentation/documentation/Xcode/localizing-and-varying-text-with-a-string-catalog].

### Add comments to text views

To ease the translation process, provide hints to translators that share how and where your app displays the strings of a [Text](Text.zh-Hans.md) view. To add a hint, use the optional `comment` parameter to the text view initializer [init(_:tableName:bundle:comment:)](Text/init___tableName_bundle_comment.zh-Hans.md). When you localize your app with Xcode, it includes the comment string along with the string. For example, the following text view includes a comment:

```swift
Text("Explore",
     comment: "The title of the tab bar item that navigates to the Explore screen.")
```

Xcode creates the following entry in your string catalog file for this view:



### Provide additional information with text views

You can localize many SwiftUI views that have a string label by providing a string that SwiftUI interprets as a [LocalizedStringKey](LocalizedStringKey.zh-Hans.md). The system uses the key to retrieve a localized value from your string catalog at runtime, or uses the string directly if it can’t find the key in the catalog. For example, SwiftUI uses the string input to the following [Label](Label.zh-Hans.md) initializer as a localized string key:

```swift
Label("Message", image: "msgSymbol")
```

If you additionally want to provide a comment for localization, you can use an explicit [Text](Text.zh-Hans.md) view instead:

```swift
Label {
    Text("Message",
         comment: "A label that displays 'Message' and a corresponding image.")
} icon: {
    Image("msgSymbol")
}
```

Many SwiftUI controls have view builder initializers that enable you to follow this pattern. For more information on how to make your app’s text translatable, see [doc://com.apple.documentation/documentation/Xcode/preparing-your-apps-text-for-translation].

## Localizing text

- **LocalizedStringKey**: The key used to look up an entry in a strings file or strings dictionary file.
- **locale**: The current locale that views should use.
- **typesettingLanguage(_:isEnabled:)**: Specifies the language for typesetting.
- **TypesettingLanguage**: Defines how typesetting language is determined for text.

