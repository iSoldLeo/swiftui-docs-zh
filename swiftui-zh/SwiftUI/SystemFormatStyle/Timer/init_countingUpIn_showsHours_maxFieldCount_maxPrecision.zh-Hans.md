---
来源：https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/Timer/init(countingUpIn:showsHours:maxFieldCount:maxPrecision:)
抓取时间：2025-12-04T13:21:26Z
---

# init(countingUpIn:showsHours:maxFieldCount:maxPrecision:)

**Initializer**

创建一个计时器格式样式，该样式向上计数至给定的时间间隔。

## 声明

```swift
init(countingUpIn interval: Range<Date>, showsHours: Bool = true, maxFieldCount: Int = 3, maxPrecision: Duration = .seconds(1))
```

## 讨论

计时器样式的显示，从 0 开始计数，直到给定的 `timerInterval`。

- 间隔：计时器向上计数的时间间隔。
- showsHours：如果为 "true"，只要持续时间至少为一小时，定时器就会在格式化字符串上以单独元素的形式显示小时数。如果为假，计时器将显示大于 60 的分钟值。
- maxFieldCount（最大字段数可同时显示的字段数。例如，1 小时 34 分钟默认显示为 `1:34:00`，但如果 `maxFieldCount`设置为 2，则显示为 `1:34`。如果较重要字段的值为零，且格式模式不需要这些字段，则样式会自动排除这些字段，为较不重要的字段腾出空间。
- maxPrecision（最大精度）：输入格式化的精度。例如，默认情况下显示秒，因此最大精度为一秒。如果将最大精度设为 `.seconds(60)`，则只能显示小时和分钟。


---
source: https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/Timer/init(countingUpIn:showsHours:maxFieldCount:maxPrecision:)
crawled: 2025-12-04T13:21:26Z
---

# init(countingUpIn:showsHours:maxFieldCount:maxPrecision:)

**Initializer**

Create a timer format style that counts up to the given interval.

## Declaration

```swift
init(countingUpIn interval: Range<Date>, showsHours: Bool = true, maxFieldCount: Int = 3, maxPrecision: Duration = .seconds(1))
```

## Discussion

A timer styled display that counts from zero up to the given `timerInterval`.

- interval: The interval during which the timer counts up.
- showsHours: If true, the timer shows the hours as a separate   element on the formatted string, as long as the duration is at least   one hour. If false, the timer displays minute values greather than sixty.
- maxFieldCount: The number of fields that can be shown at once. For example, 1 hour, 34 minutes is shown as `1:34:00` by default, but as `1:34` if the `maxFieldCount` is set to two. The style automatically excludes more significant fields if their value is zero and they are not necessary for the format pattern, making room for less significant fields.
- maxPrecision: The precision at which the input is formatted. E.g. by default, seconds are shown, making the maximum precision   one second. Setting the maximum precision to `.seconds(60)` would   only allow hours and minutes to be shown.

