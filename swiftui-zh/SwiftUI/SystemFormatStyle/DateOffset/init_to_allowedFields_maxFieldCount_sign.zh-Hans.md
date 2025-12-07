---
来源：https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/DateOffset/init(to:allowedFields:maxFieldCount:sign:)
抓取时间：2025-12-04T13:21:09Z
---

# init(to:allowedFields:maxFieldCount:sign:)

**Initializer**

创建格式样式以显示到某个日期的偏移量。

## 声明

```swift
init(to anchor: Date, allowedFields: Set<Date.ComponentsFormatStyle.Field> = [.year, .month, .week, .day, .hour, .minute, .second], maxFieldCount: Int = 2, sign: NumberFormatStyleConfiguration.SignDisplayStrategy = .automatic)
```

## 参数

- **anchor**：从格式输入开始测量的偏移日期。
- **allowedFields**：格式中可用于表示偏移量的时间单位。
- **maxFieldCount**：可同时显示的字段数。例如，1 小时 34 分 23 秒默认显示为 `1 hour, 34 minutes`，但如果 `maxFieldCount`设置为 1，则显示为 `1 hour`。
- **sign**：用于显示偏移是指向未来还是过去的标志的策略。

### 讨论

时间格式 (`3:46`) 只用于显示分、秒或时、分、秒。否则，将使用日历单位，从而产生类似 `3 months, 11 days`的输出结果。

如果格式化后的`date` 大于此处指定的`anchor`，则`anchor` 的偏移为 "正"。相反，如果输入的`date`小于`anchor`，则显示 "负 "偏移。


---
source: https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/DateOffset/init(to:allowedFields:maxFieldCount:sign:)
crawled: 2025-12-04T13:21:09Z
---

# init(to:allowedFields:maxFieldCount:sign:)

**Initializer**

Create a format style to display the offset to a certain date.

## Declaration

```swift
init(to anchor: Date, allowedFields: Set<Date.ComponentsFormatStyle.Field> = [.year, .month, .week, .day, .hour, .minute, .second], maxFieldCount: Int = 2, sign: NumberFormatStyleConfiguration.SignDisplayStrategy = .automatic)
```

## Parameters

- **anchor**: The date the offset is measured to from the format input.
- **allowedFields**: The units of time that may be used in the format to express the offset.
- **maxFieldCount**: The number of fields that can be shown at once. For example, 1 hour, 34 minutes, and 23 seconds is shown as `1 hour, 34 minutes` by default, but as `1 hour` if the `maxFieldCount` is set to one.
- **sign**: The strategy for displaying a sign to signal whether the offset points to ward the future or past.

## Discussion

The time format (`3:46`) is used as long as only minutes and seconds, or hours, minutes, and second may be shown. Otherwise, calendar units are used, resulting in outputs like `3 months, 11 days`.

The offset to the `anchor` is “positive” if the formatted `date` is greater than the given `anchor` specified here. Conversely, “negative” offsets are displayed if the input `date` is smaller than the `anchor`.

