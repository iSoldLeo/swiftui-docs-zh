--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(timerInterval:countsDown:)

抓取时间：2025-12-03T05:43:48Z

---

# init(timerInterval:countsDown:)

**Initializer**

创建一个进度视图，用于显示随时间推移而持续的进度。

## 声明

```swift
nonisolated init(timerInterval: ClosedRange<Date>, countsDown: Bool = true)
```

## 参数

- **timerInterval**：视图显示进度的日期范围。

- **countsDown**：如果为 `true`（默认值），则视图会随着时间推移而清空。

## 说明

使用此初始化器创建一个视图，用于显示指定日期范围内的持续进度。以下示例初始化一个进度视图，其范围为`start...end`，其中`start`表示过去30秒，`end`表示未来90秒。因此，进度视图从25%的完成度开始。

```swift
struct ContentView: View {
    let start = Date().addingTimeInterval(-30)
    let end = Date().addingTimeInterval(90)

    var body: some View {
        ProgressView(interval: start...end
                     countsDown: false)
    }
}
```

默认情况下，进度视图会随着时间从日期范围的开始到结束逐渐清空，但您可以使用`countsDown`参数创建一个随着时间推移逐渐填充的进度视图，如上面的示例所示。

此初始化程序提供的进度视图省略了描述性标签，并提供了一个文本标签，该标签会自动更新以描述当前剩余时间。要为这些标签提供自定义视图，请改用[init(value:total:label:currentValueLabel:)](init_value_total_label_currentValueLabel.zh-Hans.md)。

## 创建跨越特定日期范围的进度视图

- **init(timerInterval:countsDown:label:)**：创建一个进度视图，用于显示随时间推移而持续的进度，并带有描述性标签。

- **init(timerInterval:countsDown:label:currentValueLabel:)**：创建一个进度视图，用于显示随时间推移而持续的进度，并带有描述性标签和当前进度标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(timerInterval:countsDown:)
crawled: 2025-12-03T05:43:48Z
---

# init(timerInterval:countsDown:)

**Initializer**

Creates a progress view for showing continuous progress as time passes.

## Declaration

```swift
nonisolated init(timerInterval: ClosedRange<Date>, countsDown: Bool = true)
```

## Parameters

- **timerInterval**: The date range over which the view progresses.
- **countsDown**: If `true` (the default), the view empties as time passes.

## Discussion

Use this initializer to create a view that shows continuous progress within a date range. The following example initializes a progress view with a range of `start...end`, where `start` is 30 seconds in the past and `end` is 90 seconds in the future. As a result, the progress view begins at 25 percent complete.

```swift
struct ContentView: View {
    let start = Date().addingTimeInterval(-30)
    let end = Date().addingTimeInterval(90)

    var body: some View {
        ProgressView(interval: start...end
                     countsDown: false)
    }
}
```



By default, the progress view empties as time passes from the start of the date range to the end, but you can use the `countsDown` parameter to create a progress view that fills as time passes, as the above example demonstrates.

The progress view provided by this initializer omits a descriptive label and provides a text label that automatically updates to describe the current time remaining. To provide custom views for these labels, use [init(value:total:label:currentValueLabel:)](init_value_total_label_currentValueLabel.zh-Hans.md) instead.



## Create a progress view spanning a date range

- **init(timerInterval:countsDown:label:)**: Creates a progress view for showing continuous progress as time passes, with a descriptive label.
- **init(timerInterval:countsDown:label:currentValueLabel:)**: Creates a progress view for showing continuous progress as time passes, with descriptive and current progress labels.

