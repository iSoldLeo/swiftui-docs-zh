--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(timerInterval:countsDown:label:currentValueLabel:)

抓取时间：2025-12-03T05:43:50Z

---

# init(timerInterval:countsDown:label:currentValueLabel:)

**Initializer**

创建一个进度视图，用于显示随时间推移而持续的进度，并带有描述性标签和当前进度标签。

## 声明

```swift
nonisolated init(timerInterval: ClosedRange<Date>, countsDown: Bool = true, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel)
```

## 参数

- **timerInterval**：视图应显示进度的日期范围。

- **countsDown**：一个布尔值，用于确定视图是随时间推移清空还是填充。如果 `true`（默认值），则视图为空。

- **label**：一个可选视图，用于描述进度视图的用途。

- **currentValueLabel**：一个显示计时器当前值的视图。

## 讨论

使用此初始化程序创建一个视图，用于显示指定日期范围内的连续进度。以下示例初始化一个进度视图，其范围为 `start...end`，其中 `start` 表示过去 30 秒，`end` 表示未来 90 秒。因此，进度视图从 25% 完成度开始显示。此示例还提供了自定义视图，用于显示描述性标签（“进度”）和显示当前值（即日期范围）的标签。

```swift
struct ContentView: View {
    let start = Date().addingTimeInterval(-30)
    let end = Date().addingTimeInterval(90)

    var body: some View {
        ProgressView(interval: start...end,
                     countsDown: false) {
            Text("Progress")
        } currentValueLabel: {
            Text(start...end)
         }
     }
}
```

默认情况下，进度视图会随着时间推移从日期范围的开始到结束逐渐清空，但您可以使用 `countsDown` 参数创建一个随着时间推移不断填充的进度视图，如上面的示例所示。

## 创建跨越日期范围的进度视图

- **init(timerInterval:countsDown:)**：创建一个进度视图，用于显示随时间推移而持续的进度。

- **init(timerInterval:countsDown:label:)**：创建一个进度视图，用于显示随时间推移而持续的进度，并带有描述性标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(timerInterval:countsDown:label:currentValueLabel:)
crawled: 2025-12-03T05:43:50Z
---

# init(timerInterval:countsDown:label:currentValueLabel:)

**Initializer**

Creates a progress view for showing continuous progress as time passes, with descriptive and current progress labels.

## Declaration

```swift
nonisolated init(timerInterval: ClosedRange<Date>, countsDown: Bool = true, @ViewBuilder label: () -> Label, @ViewBuilder currentValueLabel: () -> CurrentValueLabel)
```

## Parameters

- **timerInterval**: The date range over which the view should progress.
- **countsDown**: A Boolean value that determines whether the view empties or fills as time passes. If `true` (the default), the view empties.
- **label**: An optional view that describes the purpose of the progress view.
- **currentValueLabel**: A view that displays the current value of the timer.

## Discussion

Use this initializer to create a view that shows continuous progress within a date range. The following example initializes a progress view with a range of `start...end`, where `start` is 30 seconds in the past and `end` is 90 seconds in the future. As a result, the progress view begins at 25 percent complete. This example also provides custom views for a descriptive label (Progress) and a current value label that shows the date range.

```swift
struct ContentView: View {
    let start = Date().addingTimeInterval(-30)
    let end = Date().addingTimeInterval(90)

    var body: some View {
        ProgressView(interval: start...end,
                     countsDown: false) {
            Text("Progress")
        } currentValueLabel: {
            Text(start...end)
         }
     }
}
```



By default, the progress view empties as time passes from the start of the date range to the end, but you can use the `countsDown` parameter to create a progress view that fills as time passes, as the above example demonstrates.



## Create a progress view spanning a date range

- **init(timerInterval:countsDown:)**: Creates a progress view for showing continuous progress as time passes.
- **init(timerInterval:countsDown:label:)**: Creates a progress view for showing continuous progress as time passes, with a descriptive label.

