--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/init(timerInterval:pauseTime:countsDown:showsHours:)

抓取时间：2025-12-01T02:39:10Z

---

# init(timerInterval:pauseTime:countsDown:showsHours:)

**Initializer**

创建一个实例，用于显示指定时间间隔内的计时器。

## 声明

```swift
init(timerInterval: ClosedRange<Date>, pauseTime: Date? = nil, countsDown: Bool = true, showsHours: Bool = true)
```

## 参数

- **timerInterval**：计时器运行的时间间隔。

- **pauseTime**：如果存在，则指定计时器暂停的日期。默认值为 `nil`，表示永不暂停。

- **countsDown**：倒计时方式（向上或向下）。默认值为 `true`。

- **showsHours**：剩余时间超过 60 分钟时，是否显示小时数。默认值为 `true`。

## 讨论

```swift
Text(
    timerInterval: Date.now...Date(timeInterval: 12 * 60, since: .now),
    pauseTime: Date.now + (10 * 60))
```

以上示例显示了一个从“12:00”开始倒计时的文本，倒计时至“10:00”时暂停。

## 创建文本视图

- **init(_:tableName:bundle:comment:)**：创建一个文本视图，用于显示由键标识的本地化内容。

- **init(_:)**：创建一个文本视图，用于显示带有样式属性的内容。

- **init(verbatim:)**：创建一个文本视图，显示不带本地化的字符串字面量。

- **init(_:style:)**：创建一个实例，使用特定样式显示本地化的日期和时间。

- **init(_:format:)**：创建一个文本视图，显示由相应格式样式支持的非字符串类型的格式化表示。

- **init(_:formatter:)**：创建一个文本视图，显示 Foundation 对象的格式化表示。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/init(timerInterval:pauseTime:countsDown:showsHours:)
crawled: 2025-12-01T02:39:10Z
---

# init(timerInterval:pauseTime:countsDown:showsHours:)

**Initializer**

Creates an instance that displays a timer counting within the provided interval.

## Declaration

```swift
init(timerInterval: ClosedRange<Date>, pauseTime: Date? = nil, countsDown: Bool = true, showsHours: Bool = true)
```

## Parameters

- **timerInterval**: The interval between where to run the timer.
- **pauseTime**: If present, the date at which to pause the timer. The default is `nil` which indicates to never pause.
- **countsDown**: Whether to count up or down. The default is `true`.
- **showsHours**: Whether to include an hours component if there are more than 60 minutes left on the timer. The default is `true`.

## Discussion

```swift
Text(
    timerInterval: Date.now...Date(timeInterval: 12 * 60, since: .now),
    pauseTime: Date.now + (10 * 60))
```

The example above shows a text that displays a timer counting down from “12:00” and will pause when reaching “10:00”.

## Creating a text view

- **init(_:tableName:bundle:comment:)**: Creates a text view that displays localized content identified by a key.
- **init(_:)**: Creates a text view that displays styled attributed content.
- **init(verbatim:)**: Creates a text view that displays a string literal without localization.
- **init(_:style:)**: Creates an instance that displays localized dates and times using a specific style.
- **init(_:format:)**: Creates a text view that displays the formatted representation of a nonstring type supported by a corresponding format style.
- **init(_:formatter:)**: Creates a text view that displays the formatted representation of a Foundation object.

