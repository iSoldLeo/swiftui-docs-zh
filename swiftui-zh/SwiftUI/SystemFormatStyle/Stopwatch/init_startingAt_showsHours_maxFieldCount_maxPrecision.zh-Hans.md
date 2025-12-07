---
来源：https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/Stopwatch/init(startingAt:showsHours:maxFieldCount:maxPrecision:)
抓取时间：2025-12-04T13:21:24Z
---

# init(startingAt:showsHours:maxFieldCount:maxPrecision:)

**Initializer**

创建秒表格式样式。

## 声明

```swift
init(startingAt startDate: Date, showsHours: Bool = true, maxFieldCount: Int = 4, maxPrecision: Duration = .milliseconds(10))
```

## 讨论

秒表式显示，从给定的 `startDate` 开始从零开始倒数。

- startDate（开始日期）：秒表开始计时的日期。
- showsHours: 显示小时数：如果为 "true"，秒表会在持续时间至少为一小时时，在格式化字符串上以单独元素显示小时。   如果为假，秒表将显示大于 60 的分钟值。
- maxFieldCount（最大字段数可同时显示的字段数。例如，1 小时 34 分钟默认显示为 `1:34:00`，但如果 `maxFieldCount`设置为 2，则显示为 `1:34`。如果较重要字段的值为零，且格式模式不需要这些字段，则样式会自动排除这些字段，为较不重要的字段腾出空间。
- maxPrecision（最大精度）：输入格式化的精度。例如，默认情况下会显示两位小数，因此最大精度为 10 毫秒。如果将最大精度设为 `.seconds(60)`，则只能显示小时和分钟。


---
source: https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/Stopwatch/init(startingAt:showsHours:maxFieldCount:maxPrecision:)
crawled: 2025-12-04T13:21:24Z
---

# init(startingAt:showsHours:maxFieldCount:maxPrecision:)

**Initializer**

Create a stopwatch format style.

## Declaration

```swift
init(startingAt startDate: Date, showsHours: Bool = true, maxFieldCount: Int = 4, maxPrecision: Duration = .milliseconds(10))
```

## Discussion

A stopwatch styled display that starts counting up from zero at the given `startDate`.

- startDate: The date at which the stopwatch starts counting.
- showsHours: If true, the stopwatch shows the hours as a separate   element on the formatted string, once the duration is at least one hour.   If false, the stopwatch displays minute values greather than sixty.
- maxFieldCount: The number of fields that can be shown at once. For example, 1 hour, 34 minutes is shown as `1:34:00` by default, but as `1:34` if the `maxFieldCount` is set to two. The style automatically excludes more significant fields if their value is zero and they are not necessary for the format pattern, making room for less significant fields.
- maxPrecision: The precision at which the input is formatted. E.g. by default, two fractional digits are shown, making the maximum precision ten milliseconds. Setting the maximum precision to `.seconds(60)` would   only allow hours and minutes to be shown.

