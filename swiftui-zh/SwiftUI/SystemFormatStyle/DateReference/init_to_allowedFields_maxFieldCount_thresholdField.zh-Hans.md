---
源：https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/DateReference/init(to:allowedFields:maxFieldCount:thresholdField:)
抓取时间：2025-12-04T13:21:16Z
---

# init(to:allowedFields:maxFieldCount:thresholdField:)

**Initializer**

创建格式样式，以最自然的方式引用日期。

## 声明

```swift
init(to date: Date, allowedFields: Set<Date.RelativeFormatStyle.Field> = [.year, .month, .day, .hour, .minute], maxFieldCount: Int = 2, thresholdField: Date.RelativeFormatStyle.Field = .day)
```

## 参数

- **date**：此格式引用的日期。
- **allowedFields**：格式中可用于表示引用的时间单位。`thresholdField`总是被假定为允许的。
- **maxFieldCount**：使用绝对格式时可同时显示的字段数。例如，2007 年 1 月 9 日默认显示为 `January 2007`，但如果 `maxFieldCount`设置为 3，则显示为 `January 9, 2007`。如果较重要的字段的值等于参考日期中的值，而格式模式又不需要这些字段，则样式会自动排除这些字段，为较不重要的字段留出空间。
- **thresholdField**：保留的字段精确度最低，因此需要将字段数从 1 增加到 1，即从相对表示法转换为绝对表示法。


---
source: https://developer.apple.com/documentation/SwiftUI/SystemFormatStyle/DateReference/init(to:allowedFields:maxFieldCount:thresholdField:)
crawled: 2025-12-04T13:21:16Z
---

# init(to:allowedFields:maxFieldCount:thresholdField:)

**Initializer**

Create a format style to refer to a date in the most natural way.

## Declaration

```swift
init(to date: Date, allowedFields: Set<Date.RelativeFormatStyle.Field> = [.year, .month, .day, .hour, .minute], maxFieldCount: Int = 2, thresholdField: Date.RelativeFormatStyle.Field = .day)
```

## Parameters

- **date**: The date this format references.
- **allowedFields**: The units of time that may be used in the format to express the reference. The `thresholdField` is always assumed to be allowed.
- **maxFieldCount**: The number of fields that can be shown at once when   using an abolute format. For example, January 9, 2007 is shown as `January 2007` by default, but as `January 9, 2007` if the `maxFieldCount` is set to three. The style automatically excludes more significant fields if their value is equal to the value in the reference date and they are not necessary for the format pattern, making room for less significant fields.
- **thresholdField**: The least precise field preserving which warrants increasing the field count from one, i.e. switching from the relative   to the absolute representation.

