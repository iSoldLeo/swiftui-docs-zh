--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(timerInterval:countsDown:label:)

抓取时间：2025-12-03T05:43:49Z

---

# init(timerInterval:countsDown:label:)

**Initializer**

创建一个进度视图，用于显示随时间推移而持续的进度，并带有描述性标签。

## 声明

```swift
nonisolated init(timerInterval: ClosedRange<Date>, countsDown: Bool = true, @ViewBuilder label: () -> Label)
```

## 参数

- **timerInterval**：视图显示进度的日期范围。

- **countsDown**：一个布尔值，用于确定视图是清空还是填充。如果为 `true`（默认值），则视图清空。

- **label**：一个可选的视图，用于描述进度视图的用途。

## 讨论

使用此初始化器创建一个视图，用于显示指定日期范围内的连续进度。以下示例初始化了一个进度视图，其范围为 `start...end`，其中 `start` 表示过去 30 秒，`end` 表示未来 90 秒。因此，进度视图从 25% 的完成度开始。此示例还提供了一个自定义的描述性标签。

```swift
struct ContentView: View {
    let start = Date().addingTimeInterval(-30)
    let end = Date().addingTimeInterval(90)

    var body: some View {
        ProgressView(interval: start...end,
                     countsDown: false) {
            Text("Progress")
         }
    }
}
```

默认情况下，进度视图会随着时间从日期范围的开始到结束逐渐清空，但您可以使用 `countsDown` 参数创建一个随着时间推移而填充的进度视图，如上面的示例所示。

此初始化程序提供的进度视图使用一个文本标签，该标签会自动更新以描述当前剩余时间。要提供自定义标签来显示当前值，请改用 [init(value:total:label:currentValueLabel:)](init_value_total_label_currentValueLabel.zh-Hans.md)。

## 创建跨越日期范围的进度视图

- **init(timerInterval:countsDown:)**：创建一个进度视图，用于显示随时间推移而持续进行的进度。

- **init(timerInterval:countsDown:label:currentValueLabel:)**：创建一个进度视图，用于显示随时间推移而持续进行的进度，并带有描述性标签和当前进度标签。


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(timerInterval:countsDown:label:)
crawled: 2025-12-03T05:43:49Z
---

# init(timerInterval:countsDown:label:)

**Initializer**

Creates a progress view for showing continuous progress as time passes, with a descriptive label.

## Declaration

```swift
nonisolated init(timerInterval: ClosedRange<Date>, countsDown: Bool = true, @ViewBuilder label: () -> Label)
```

## Parameters

- **timerInterval**: The date range over which the view progresses.
- **countsDown**: A Boolean value that determines whether the view empties or fills as time passes. If `true` (the default), the view empties.
- **label**: An optional view that describes the purpose of the progress view.

## Discussion

Use this initializer to create a view that shows continuous progress within a date range. The following example initializes a progress view with a range of `start...end`, where `start` is 30 seconds in the past and `end` is 90 seconds in the future. As a result, the progress view begins at 25 percent complete. This example also provides a custom descriptive label.

```swift
struct ContentView: View {
    let start = Date().addingTimeInterval(-30)
    let end = Date().addingTimeInterval(90)

    var body: some View {
        ProgressView(interval: start...end,
                     countsDown: false) {
            Text("Progress")
         }
    }
}
```



By default, the progress view empties as time passes from the start of the date range to the end, but you can use the `countsDown` parameter to create a progress view that fills as time passes, as the above example demonstrates.

The progress view provided by this initializer uses a text label that automatically updates to describe the current time remaining. To provide a custom label to show the current value, use [init(value:total:label:currentValueLabel:)](init_value_total_label_currentValueLabel.zh-Hans.md) instead.



## Create a progress view spanning a date range

- **init(timerInterval:countsDown:)**: Creates a progress view for showing continuous progress as time passes.
- **init(timerInterval:countsDown:label:currentValueLabel:)**: Creates a progress view for showing continuous progress as time passes, with descriptive and current progress labels.

