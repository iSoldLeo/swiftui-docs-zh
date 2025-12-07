--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:formatter:)

抓取时间：2025-12-04T13:21:50Z

---

# appendInterpolation(_:formatter:)

**实例方法**

将 Objective-C 子类的可选格式化实例追加到字符串插值中。

## 声明

```swift
mutating func appendInterpolation<Subject>(_ subject: Subject, formatter: Formatter? = nil) where Subject : NSObject
```

## 参数

- **subject**：要追加的 [doc://com.apple.documentation/documentation/ObjectiveC/NSObject-swift.class]。

- **formatter**：用于将 `subject` 转换为字符串表示形式的格式化程序。

## 说明

请勿直接调用此方法；编译器在解释字符串插值时会用到它。

以下示例展示了如何使用 [doc://com.apple.documentation/documentation/Foundation/Measurement] 值和 [doc://com.apple.documentation/documentation/Foundation/MeasurementFormatter] 来创建一个 [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md)，该 [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md) 在生成测量值的字符串表示时使用格式化样式 [doc://com.apple.documentation/documentation/Foundation/Formatter/UnitStyle/long]。代码并没有直接调用 `appendInterpolation(_:formatter)`，而是通过使用 `\()` 字符串插值语法隐式地获取格式化行为。

```swift
let siResistance = Measurement(value: 640, unit: UnitElectricResistance.ohms)
let formatter = MeasurementFormatter()
formatter.unitStyle = .long
let key = LocalizedStringKey ("Resistance: \(siResistance, formatter: formatter)")
let text1 = Text(key) // Text contains "Resistance: 640 ohms"
```

## 向插值追加内容

- **appendInterpolation(_:)**：将属性字符串追加到字符串插值中。

- **appendInterpolation(_:specifier:)**：将可转换为字符串的类型（带有格式说明符）附加到字符串插值中。

- **appendInterpolation(_:format:)**：附加由相应格式样式支持的非字符串类型的格式化表示形式。

- **appendInterpolation(_:style:)**：将格式化的日期附加到字符串插值中。

- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**：将计时器间隔附加到字符串插值中。

- **appendLiteral(_:)**：附加字符串字面值。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(_:formatter:)
crawled: 2025-12-04T13:21:50Z
---

# appendInterpolation(_:formatter:)

**Instance Method**

Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.

## Declaration

```swift
mutating func appendInterpolation<Subject>(_ subject: Subject, formatter: Formatter? = nil) where Subject : NSObject
```

## Parameters

- **subject**: An [doc://com.apple.documentation/documentation/ObjectiveC/NSObject-swift.class] to append.
- **formatter**: A formatter to convert `subject` to a string representation.

## Discussion

Don’t call this method directly; it’s used by the compiler when interpreting string interpolations.

The following example shows how to use a [doc://com.apple.documentation/documentation/Foundation/Measurement] value and a [doc://com.apple.documentation/documentation/Foundation/MeasurementFormatter] to create a [LocalizedStringKey](../../LocalizedStringKey.zh-Hans.md) that uses the formatter style [doc://com.apple.documentation/documentation/Foundation/Formatter/UnitStyle/long] when generating the measurement’s string representation. Rather than calling `appendInterpolation(_:formatter)` directly, the code gets the formatting behavior implicitly by using the `\()` string interpolation syntax.

```swift
let siResistance = Measurement(value: 640, unit: UnitElectricResistance.ohms)
let formatter = MeasurementFormatter()
formatter.unitStyle = .long
let key = LocalizedStringKey ("Resistance: \(siResistance, formatter: formatter)")
let text1 = Text(key) // Text contains "Resistance: 640 ohms"
```

## Appending to an interpolation

- **appendInterpolation(_:)**: Appends an attributed string to a string interpolation.
- **appendInterpolation(_:specifier:)**: Appends a type, convertible to a string with a format specifier, to a string interpolation.
- **appendInterpolation(_:format:)**: Appends the formatted representation  of a nonstring type supported by a corresponding format style.
- **appendInterpolation(_:style:)**: Appends a formatted date to a string interpolation.
- **appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)**: Appends a timer interval to a string interpolation.
- **appendLiteral(_:)**: Appends a literal string.

