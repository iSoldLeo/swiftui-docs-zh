--- 来源：https://developer.apple.com/documentation/SwiftUI/TypesettingLanguage
抓取时间：2025-12-02T17:35:44Z

---

# TypesettingLanguage

**Structure**

定义文本排版语言的确定方式。

## 声明

```swift
struct TypesettingLanguage
```

## 概述

使用类似 [typesettingLanguage(_:isEnabled:)](View/typesettingLanguage___isEnabled.zh-Hans.md) 的修饰符来指定排版语言。

## 获取语言行为

- **automatic**：自动语言行为。

- **explicit(_:)**：使用显式语言。

## 文本本地化

- **为本地化准备视图**：指定提示并添加字符串以本地化您的 SwiftUI 视图。

- **LocalizedStringKey**：用于在字符串文件或字符串字典文件中查找条目的键。

- **locale**：视图当前应使用的区域设置。

- **typesettingLanguage(_:isEnabled:)**：指定排版语言。

## 符合以下标准

- Equatable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/TypesettingLanguage
crawled: 2025-12-02T17:35:44Z
---

# TypesettingLanguage

**Structure**

Defines how typesetting language is determined for text.

## Declaration

```swift
struct TypesettingLanguage
```

## Overview

Use a modifier like [typesettingLanguage(_:isEnabled:)](View/typesettingLanguage___isEnabled.zh-Hans.md) to specify the typesetting language.

## Getting language behavior

- **automatic**: Automatic language behavior.
- **explicit(_:)**: Use explicit language.

## Localizing text

- **Preparing views for localization**: Specify hints and add strings to localize your SwiftUI views.
- **LocalizedStringKey**: The key used to look up an entry in a strings file or strings dictionary file.
- **locale**: The current locale that views should use.
- **typesettingLanguage(_:isEnabled:)**: Specifies the language for typesetting.

## Conforms To

- Equatable
- Sendable
- SendableMetatype

