--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:specifier:)

抓取时间：2025-12-04T13:21:49Z

---

# appendInterpolation(_:specifier:)

**实例方法**

将一个可转换为带有格式说明符的字符串的类型添加到字符串插值中。

## 声明

```swift
mutating func appendInterpolation<T>(_ value: T, specifier: String) where T : _FormatSpecifiable
```

## 参数

- **value**：要添加的值。

- **specifier**：用于将 `subject` 转换为字符串表示形式的格式说明符，例如将 [doc://com.apple.documentation/documentation/Swift/Double] 转换为 `%f`，或将 [doc://com.apple.documentation/documentation/Swift/UInt32] 转换为十六进制表示形式，使用 `%x`。有关可用格式说明符字符串的列表，请参阅 [https://developer.apple.com/library/archive/documentation/CoreFoundation/Conceptual/CFStrings/formatSpecifiers.html#//apple_ref/doc/uid/TP40004265]。

## 讨论

请勿直接调用此方法；编译器在解释字符串插值时会使用此方法。

## 向字符串插值添加内容

- **appendInterpolation(_:)**：向字符串插值添加带属性的字符串。

- **appendInterpolation(_:format:)**：向字符串插值添加由相应格式样式支持的非字符串类型的格式化表示形式。

- **appendInterpolation(_:formatter:)**：向字符串插值添加 Objective-C 子类的可选格式化实例。

- **appendInterpolation(_:style:)**：向字符串插值添加格式化的日期。

- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**：向字符串插值添加定时器间隔。

- **appendLiteral(_:)**：向字符串插值添加字面字符串。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:specifier:)
crawled: 2025-12-04T13:21:49Z
---

# appendInterpolation(_:specifier:)

**Instance Method**

Appends a type, convertible to a string with a format specifier, to a string interpolation.

## Declaration

```swift
mutating func appendInterpolation<T>(_ value: T, specifier: String) where T : _FormatSpecifiable
```

## Parameters

- **value**: The value to append.
- **specifier**: A format specifier to convert `subject` to a string representation, like `%f` for a [doc://com.apple.documentation/documentation/Swift/Double], or `%x` to create a hexidecimal representation of a [doc://com.apple.documentation/documentation/Swift/UInt32]. For a list of available specifier strings, see [https://developer.apple.com/library/archive/documentation/CoreFoundation/Conceptual/CFStrings/formatSpecifiers.html#//apple_ref/doc/uid/TP40004265].

## Discussion

Don’t call this method directly; it’s used by the compiler when interpreting string interpolations.

## Appending to an interpolation

- **appendInterpolation(_:)**: Appends an attributed string to a string interpolation.
- **appendInterpolation(_:format:)**: Appends the formatted representation  of a nonstring type supported by a corresponding format style.
- **appendInterpolation(_:formatter:)**: Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.
- **appendInterpolation(_:style:)**: Appends a formatted date to a string interpolation.
- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**: Appends a timer interval to a string interpolation.
- **appendLiteral(_:)**: Appends a literal string.

