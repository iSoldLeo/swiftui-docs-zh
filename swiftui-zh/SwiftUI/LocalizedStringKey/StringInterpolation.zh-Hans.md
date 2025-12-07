--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation
抓取时间：2025-12-03T06:19:42Z

---

# LocalizedStringKey.StringInterpolation

**Structure**

在构建字符串字面量时，使用插值来表示其内容，用于创建本地化字符串键。

## 声明

```swift
struct StringInterpolation
```

## 向插值字符串追加内容

- **appendInterpolation(_:)**：向字符串插值字符串追加一个带属性的字符串。

- **appendInterpolation(_:specifier:)**：向字符串插值字符串追加一个可转换为字符串的类型（带有格式说明符）。

- **appendInterpolation(_:format:)**：将支持相应格式样式的非字符串类型的格式化表示形式附加到字符串插值中。

- **appendInterpolation(_:formatter:)**：将 Objective-C 子类的可选格式化实例附加到字符串插值中。

- **appendInterpolation(_:style:)**：将格式化日期附加到字符串插值中。

- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**：将定时器间隔附加到字符串插值中。

- **appendLiteral(_:)**：附加字符串字面量。

## 实例方法

- **appendInterpolation(accessibilityName:)**：将用于辅助功能的本地化颜色描述附加到字符串插值中。

## 从插值创建键

- **init(stringInterpolation:)**：根据给定的字符串插值创建本地化字符串键。

## 符合以下协议：

- StringInterpolationProtocol


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation
crawled: 2025-12-03T06:19:42Z
---

# LocalizedStringKey.StringInterpolation

**Structure**

Represents the contents of a string literal with interpolations while it’s being built, for use in creating a localized string key.

## Declaration

```swift
struct StringInterpolation
```

## Appending to an interpolation

- **appendInterpolation(_:)**: Appends an attributed string to a string interpolation.
- **appendInterpolation(_:specifier:)**: Appends a type, convertible to a string with a format specifier, to a string interpolation.
- **appendInterpolation(_:format:)**: Appends the formatted representation  of a nonstring type supported by a corresponding format style.
- **appendInterpolation(_:formatter:)**: Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.
- **appendInterpolation(_:style:)**: Appends a formatted date to a string interpolation.
- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**: Appends a timer interval to a string interpolation.
- **appendLiteral(_:)**: Appends a literal string.

## Instance Methods

- **appendInterpolation(accessibilityName:)**: Appends a localized description of a color for accessibility to a string interpolation.

## Creating a key from an interpolation

- **init(stringInterpolation:)**: Creates a localized string key from the given string interpolation.

## Conforms To

- StringInterpolationProtocol

