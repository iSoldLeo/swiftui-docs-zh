---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityTextContentType
抓取时间： 2025-12-02T17:44:18Z
---

# 可访问性文本内容类型

**Structure**

辅助技术可用于改善口语文本呈现效果的文本上下文。

## 声明

```swift
struct AccessibilityTextContentType
```

## 概览

使用[accessibilityTextContentType(_:)](View/accessibilityTextContentType.zh-Hans.md)修饰符设置视图的辅助功能文本内容类型时，请使用`AccessibilityTextContentType`值。

## 获取内容类型

- **console**：表示用于输入的文本的类型，如在终端应用程序中。
- **fileSystem**：表示文件浏览器（如 macOS 中的 Finder 应用程序）所用文本的类型。
- **messaging**：表示信息中使用的文本的类型，如在 "信息 "应用程序中。
- **narrative**：表示故事或诗歌中使用的文本的类型，如在 Books app 中。
- **plain**：表示没有特定类型的通用文本的类型。
- **sourceCode**：表示源代码中使用的文本的类型，如在 Swift Playgrounds 中。
- **spreadsheet**：表示数据网格中使用的文本的类型，如在 Numbers 应用程序中。
- **wordProcessing**：表示文档中使用的文本的类型，如 Pages 应用程序。

## 描述内容

- **accessibilityTextContentType(_:)**：设置辅助功能文本内容类型。
- **accessibilityHeading(_:)**：设置此标题的辅助功能级别。
- **AccessibilityHeadingLevel**：标题相对于其他标题的等级。

## 符合

- 可发送
- 可发送元数据类型


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityTextContentType
crawled: 2025-12-02T17:44:18Z
---

# AccessibilityTextContentType

**Structure**

Textual context that assistive technologies can use to improve the presentation of spoken text.

## Declaration

```swift
struct AccessibilityTextContentType
```

## Overview

Use an `AccessibilityTextContentType` value when setting the accessibility text content type of a view using the [accessibilityTextContentType(_:)](View/accessibilityTextContentType.zh-Hans.md) modifier.

## Getting content types

- **console**: A type that represents text used for input, like in the Terminal app.
- **fileSystem**: A type that represents text used by a file browser, like in the Finder app in macOS.
- **messaging**: A type that represents text used in a message, like in the Messages app.
- **narrative**: A type that represents text used in a story or poem, like in the Books app.
- **plain**: A type that represents generic text that has no specific type.
- **sourceCode**: A type that represents text used in source code, like in Swift Playgrounds.
- **spreadsheet**: A type that represents text used in a grid of data, like in the Numbers app.
- **wordProcessing**: A type that represents text used in a document, like in the Pages app.

## Describing content

- **accessibilityTextContentType(_:)**: Sets an accessibility text content type.
- **accessibilityHeading(_:)**: Sets the accessibility level of this heading.
- **AccessibilityHeadingLevel**: The hierarchy of a heading in relation to other headings.

## Conforms To

- Sendable
- SendableMetatype

