--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:style:)

抓取时间：2025-12-04T13:21:51Z

---

# appendInterpolation(_:style:)

**实例方法**

将格式化的日期追加到字符串插值中。

## 声明

```swift
mutating func appendInterpolation(_ date: Date, style: Text.DateStyle)
```

## 参数

- **date**：要追加的日期。

- **style**：用于格式化日期的预定义样式。

## 说明

请勿直接调用此方法；编译器在解释字符串插值时会使用它。

## 向字符串插值添加内容

- **appendInterpolation(_:)**：向字符串插值添加一个带属性的字符串。

- **appendInterpolation(_:specifier:)**：向字符串插值添加一个可转换为字符串的类型（需指定格式说明符）。

- **appendInterpolation(_:format:)**：向字符串插值添加一个非字符串类型的格式化表示形式（需指定格式）。

- **appendInterpolation(_:formatter:)**：向字符串插值添加一个 Objective-C 子类的可选格式化实例。

- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**：向字符串插值添加一个定时器间隔。

- **appendLiteral(_:)**：向字符串插值添加一个字符串字面量。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:style:)
crawled: 2025-12-04T13:21:51Z
---

# appendInterpolation(_:style:)

**Instance Method**

Appends a formatted date to a string interpolation.

## Declaration

```swift
mutating func appendInterpolation(_ date: Date, style: Text.DateStyle)
```

## Parameters

- **date**: The date to append.
- **style**: A predefined style to format the date with.

## Discussion

Don’t call this method directly; it’s used by the compiler when interpreting string interpolations.

## Appending to an interpolation

- **appendInterpolation(_:)**: Appends an attributed string to a string interpolation.
- **appendInterpolation(_:specifier:)**: Appends a type, convertible to a string with a format specifier, to a string interpolation.
- **appendInterpolation(_:format:)**: Appends the formatted representation  of a nonstring type supported by a corresponding format style.
- **appendInterpolation(_:formatter:)**: Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.
- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**: Appends a timer interval to a string interpolation.
- **appendLiteral(_:)**: Appends a literal string.

