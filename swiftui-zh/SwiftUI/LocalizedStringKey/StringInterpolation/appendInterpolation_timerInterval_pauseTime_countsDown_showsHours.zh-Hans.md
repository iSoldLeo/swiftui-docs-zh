--- 来源：https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)

抓取时间：2025-12-04T13:21:52Z

---

# appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)

**实例方法**

将定时器间隔添加到字符串插值中。

## 声明

```swift
mutating func appendInterpolation(timerInterval: ClosedRange<Date>, pauseTime: Date? = nil, countsDown: Bool = true, showsHours: Bool = true)
```

## 参数

- **timerInterval**：定时器运行的间隔。

- **pauseTime**：如果存在，则指定定时器暂停的日期。默认值为 `nil`，表示永不暂停。

- **countsDown**：向上计数还是向下计数。默认值为 `true`。

- **showsHours**：如果计时器剩余时间超过 60 分钟，是否包含小时数。默认值为 `true`。

## 讨论

请勿直接调用此方法；编译器在解释字符串插值时会用到它。

## 向插值追加内容

- **appendInterpolation(_:)**：向字符串插值追加一个带属性的字符串。

- **appendInterpolation(_:specifier:)**：向字符串插值追加一个可转换为字符串的类型（带有格式说明符）。

- **appendInterpolation(_:format:)**：向字符串插值追加一个由相应格式样式支持的非字符串类型的格式化表示形式。

- **appendInterpolation(_:formatter:)**：将一个可选格式化的 Objective-C 子类实例追加到字符串插值中。

- **appendInterpolation(_:style:)**：将一个格式化的日期追加到字符串插值中。

- **appendLiteral(_:)**：追加一个字符串字面值。


---
source: https://developer.apple.com/documentation/SwiftUI/LocalizedStringKey/StringInterpolation/appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)
crawled: 2025-12-04T13:21:52Z
---

# appendInterpolation(timerInterval:pauseTime:countsDown:showsHours:)

**Instance Method**

Appends a timer interval to a string interpolation.

## Declaration

```swift
mutating func appendInterpolation(timerInterval: ClosedRange<Date>, pauseTime: Date? = nil, countsDown: Bool = true, showsHours: Bool = true)
```

## Parameters

- **timerInterval**: The interval between where to run the timer.
- **pauseTime**: If present, the date at which to pause the timer. The default is `nil` which indicates to never pause.
- **countsDown**: Whether to count up or down. The default is `true`.
- **showsHours**: Whether to include an hours component if there are more than 60 minutes left on the timer. The default is `true`.

## Discussion

Don’t call this method directly; it’s used by the compiler when interpreting string interpolations.

## Appending to an interpolation

- **appendInterpolation(_:)**: Appends an attributed string to a string interpolation.
- **appendInterpolation(_:specifier:)**: Appends a type, convertible to a string with a format specifier, to a string interpolation.
- **appendInterpolation(_:format:)**: Appends the formatted representation  of a nonstring type supported by a corresponding format style.
- **appendInterpolation(_:formatter:)**: Appends an optionally-formatted instance of an Objective-C subclass to a string interpolation.
- **appendInterpolation(_:style:)**: Appends a formatted date to a string interpolation.
- **appendLiteral(_:)**: Appends a literal string.

