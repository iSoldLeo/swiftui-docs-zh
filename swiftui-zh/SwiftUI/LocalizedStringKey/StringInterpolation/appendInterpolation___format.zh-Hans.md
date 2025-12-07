--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:format:)

抓取时间：2025-12-04T13:21:49Z

---

# appendInterpolation(_:format:)

**实例方法**

追加由相应格式样式支持的非字符串类型的格式化表示。

## 声明

```swift
mutating func appendInterpolation<F>(_ input: F.FormatInput, format: F) where F : FormatStyle, F.FormatInput : Equatable, F.FormatOutput == AttributedString
```

## 参数

- **input**：要格式化并追加的实例。

- **format**：将 `input` 转换为带属性的字符串表示时要使用的格式样式。

## 说明

不要直接调用此方法；编译器在解释字符串插值时会使用它。

以下示例展示了如何使用字符串插值将 [doc://com.apple.documentation/documentation/Foundation/Date] 格式化为 [doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle] 并将其附加到静态文本。生成的插值会隐式地创建一个 [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md)，[Text](../../Text.zh-Hans.md) 使用该 [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md) 来提供其内容。

```swift
Text("The time is \(myDate, format: Date.FormatStyle(date: .omitted, time:.complete).attributedStyle)")
```

## 向插值追加内容

- **appendInterpolation(_:)**：将带属性的字符串附加到字符串插值。

- **appendInterpolation(_:specifier:)**：将可转换为带格式说明符的字符串的类型附加到字符串插值。

- **appendInterpolation(_:formatter:)**：将 Objective-C 子类的可选格式化实例附加到字符串插值。

- **appendInterpolation(_:style:)**：将格式化日期附加到字符串插值中。

- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**：将定时器间隔附加到字符串插值中。

- **appendLiteral(_:)**：附加一个字符串字面值。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:format:)
crawled: 2025-12-04T13:21:49Z
---

# appendInterpolation(_:format:)

**Instance Method**

Appends the formatted representation  of a nonstring type supported by a corresponding format style.

## Declaration

```swift
mutating func appendInterpolation<F>(_ input: F.FormatInput, format: F) where F : FormatStyle, F.FormatInput : Equatable, F.FormatOutput == AttributedString
```

## Parameters

- **input**: The instance to format and append.
- **format**: A format style to use when converting `input` into an attributed string representation.

## Discussion

Don’t call this method directly; it’s used by the compiler when interpreting string interpolations.

The following example shows how to use a string interpolation to format a [doc://com.apple.documentation/documentation/Foundation/Date] with a [doc://com.apple.documentation/documentation/Foundation/Date/FormatStyle] and append it to static text. The resulting interpolation implicitly creates a [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md), which a [Text](../../Text.zh-Hans.md) uses to provide its content.

```swift
Text("The time is \(myDate, format: Date.FormatStyle(date: .omitted, time:.complete).attributedStyle)")
```

## Appending to an interpolation

- **appendInterpolation(_:)**: Appends an attributed string to a string interpolation.
- **appendInterpolation(_:specifier:)**: Appends a type, convertible to a string with a format specifier, to a string interpolation.
- **appendInterpolation(_:formatter:)**: Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.
- **appendInterpolation(_:style:)**: Appends a formatted date to a string interpolation.
- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**: Appends a timer interval to a string interpolation.
- **appendLiteral(_:)**: Appends a literal string.

