--- 来源：https://developer.apple.com/documentation/SwiftUI/Font/Resolved
抓取时间：2025-12-03T06:18:16Z

---

# Font.Resolved

**Structure**

一个具体的字体值。

## 声明

```swift
struct Resolved
```

## 概述

`Font.Resolved` 是一个具体的字体表示，它具有一组特定的 `EnvironmentValues`。在给定的平台上，`Resolved` 字体始终映射到相同的 CTFont。

## 实例属性

- **ctFont**：返回表示 CoreText 字体对象的 CTFont 不透明类型。

- **isBold**：如果解析后的字体根据 CoreText 具有粗体特征，或者字体粗细为半粗体或更粗，则返回 `true`。

- **isItalic**：如果解析后的字体是斜体，则返回 `true`。

- **isLowercaseSmallCaps**：如果解析后的字体的小写字母使用小型大写字母，则返回 `true`。

- **isMonospaced**：如果解析后的字体是等宽字体，则返回 `true`，否则返回 false。

- **isSmallCaps**：如果解析后的字体的所有字符都使用小型大写字母，则返回 `true`。

- **isUppercaseSmallCaps**：如果解析后的字体的大写字母使用小型大写字母，则返回 `true`。

- **leading**：解析后的字体的行距。

- **pointSize**：解析后的字体的磅值。

- **weight**：解析后的字体的粗细。

- **width**：解析后的字体的宽度。

## 符合以下标准

- Equatable

- Hashable

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/Font/Resolved
crawled: 2025-12-03T06:18:16Z
---

# Font.Resolved

**Structure**

A concrete font value.

## Declaration

```swift
struct Resolved
```

## Overview

`Font.Resolved` is a concrete representation of a Font that can be shown, with a specific set of `EnvironmentValues`. A `Resolved` font will always map to the same CTFont on a given platform.



## Instance Properties

- **ctFont**: Returns the CTFont opaque type that represents a CoreText font object.
- **isBold**: Returns `true` if the resolved font has a bold trait according to CoreText or the font’s weight is semi-bold or greater.
- **isItalic**: Returns `true` if the resolved font is italic.
- **isLowercaseSmallCaps**: Returns `true` if the resolved font’s lowercased characters use small caps.
- **isMonospaced**: Returns `true` if a resolved font is monospaced, false otherwise.
- **isSmallCaps**: Returns `true` if all of the resolved font’s characters use small caps.
- **isUppercaseSmallCaps**: Returns `true` if the resolved font’s uppercased characters use small caps.
- **leading**: The leading of a resolved font.
- **pointSize**: The point size of a resolved font.
- **weight**: The weight of a resolved font.
- **width**: The width of a resolved font.

## Conforms To

- Equatable
- Hashable
- Sendable
- SendableMetatype

