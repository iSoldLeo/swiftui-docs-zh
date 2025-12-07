--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendLiteral(_:)

抓取时间：2025-12-04T13:21:53Z

---

# appendLiteral(_:)

**实例方法**

追加一个字符串字面量。

## 声明

```swift
mutating func appendLiteral(_ literal: String)
```

## 参数

- **literal**：要追加的字符串字面量。

## 说明

不要直接调用此方法；编译器在解释字符串插值时会用到它。

## 追加到插值中

- **appendInterpolation(_:)**：将一个带属性的字符串追加到字符串插值中。

- **appendInterpolation(_:specifier:)**：将可转换为字符串的类型（带有格式说明符）附加到字符串插值中。

- **appendInterpolation(_:format:)**：将受相应格式样式支持的非字符串类型的格式化表示形式附加到字符串插值中。

- **appendInterpolation(_:formatter:)**：将 Objective-C 子类的可选格式化实例附加到字符串插值中。

- **appendInterpolation(_:style:)**：将格式化的日期附加到字符串插值中。

- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**：将计时器间隔附加到字符串插值中。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendLiteral(_:)
crawled: 2025-12-04T13:21:53Z
---

# appendLiteral(_:)

**Instance Method**

Appends a literal string.

## Declaration

```swift
mutating func appendLiteral(_ literal: String)
```

## Parameters

- **literal**: The literal string to append.

## Discussion

Don’t call this method directly; it’s used by the compiler when interpreting string interpolations.

## Appending to an interpolation

- **appendInterpolation(_:)**: Appends an attributed string to a string interpolation.
- **appendInterpolation(_:specifier:)**: Appends a type, convertible to a string with a format specifier, to a string interpolation.
- **appendInterpolation(_:format:)**: Appends the formatted representation  of a nonstring type supported by a corresponding format style.
- **appendInterpolation(_:formatter:)**: Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.
- **appendInterpolation(_:style:)**: Appends a formatted date to a string interpolation.
- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**: Appends a timer interval to a string interpolation.

