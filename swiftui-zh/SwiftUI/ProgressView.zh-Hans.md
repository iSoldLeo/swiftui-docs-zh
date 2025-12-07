--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView

抓取时间：2025-12-02T17:27:39Z

---

# ProgressView

**Structure**

用于显示任务完成进度的视图。

## 声明

```swift
struct ProgressView<Label, CurrentValueLabel> where Label : View, CurrentValueLabel : View
```

## 概述

使用进度视图来显示任务尚未完成但正在推进。进度视图可以显示确定型（完成百分比）和不确定型（进行中或未进行中）的进度。

要创建确定型进度视图，请初始化一个 `ProgressView`，并将其绑定到一个表示进度的数值，以及一个 `total`，该值表示任务的完成状态。默认情况下，进度为`0.0`，总计为`1.0`。

以下示例使用状态属性`progress`在确定的`ProgressView`中显示进度。进度视图使用其默认总计`1.0`，并且由于`progress`的初始值为`0.5`，因此进度视图开始时显示已完成一半。进度视图下方的“更多”按钮允许用户以 5% 的增量增加进度：

```swift
struct LinearProgressDemoView: View {
    @State private var progress = 0.5

    var body: some View {
        VStack {
            ProgressView(value: progress)
            Button("More") { progress += 0.05 }
        }
    }
}
```

要创建不确定进度的视图，请使用不接受进度值的初始化器：

```swift
var body: some View {
    ProgressView()
}
```

您还可以创建涵盖封闭值范围的进度视图。[doc://com.apple.documentation/documentation/Foundation/Date] 只要当前日期在该范围内，进度视图就会自动更新，并在接近范围末尾时填充或清空进度视图。以下示例显示了一个五分钟计时器，其开始时间为进度视图的初始化时间：

```swift
struct DateRelativeProgressDemoView: View {
    let workoutDateRange = Date()...Date().addingTimeInterval(5*60)

    var body: some View {
         ProgressView(timerInterval: workoutDateRange) {
             Text("Workout")
         }
    }
}
```

### 自定义进度视图样式

您可以通过创建符合 [ProgressViewStyle](ProgressViewStyle.zh-Hans.md) 协议的样式来自定义进度视图的外观和交互。要为视图内的所有进度视图实例设置特定样式，请使用 [progressViewStyle(_:)](View/progressViewStyle.zh-Hans.md) 修饰符。在以下示例中，自定义样式为包含 [VStack](VStack.zh-Hans.md) 的所有进度视图添加了圆角粉色边框：

```swift
struct BorderedProgressViews: View {
    var body: some View {
        VStack {
            ProgressView(value: 0.25) { Text("25% progress") }
            ProgressView(value: 0.75) { Text("75% progress") }
        }
        .progressViewStyle(PinkBorderedProgressViewStyle())
    }
}

struct PinkBorderedProgressViewStyle: ProgressViewStyle {
    func makeBody(configuration: Configuration) -> some View {
        ProgressView(configuration)
            .padding(4)
            .border(.pink, width: 3)
            .cornerRadius(4)
    }
}
```

SwiftUI 提供了两种内置的进度视图样式：[linear](ProgressViewStyle/linear.zh-Hans.md) 和 [circular](ProgressViewStyle/circular.zh-Hans.md)，以及一种自动样式，该样式默认使用当前上下文中最合适的样式。以下示例显示了一个从 60% 完成度开始的圆形进度视图。

```swift
struct CircularProgressDemoView: View {
    @State private var progress = 0.6

    var body: some View {
        VStack {
            ProgressView(value: progress)
                .progressViewStyle(.circular)
        }
    }
}
```

在 macOS 以外的平台上，圆形样式可能显示为不确定的指示器。

## 创建不确定进度视图

- **init()**：创建一个用于显示不确定进度且不带标签的进度视图。

- **init(label:)**：创建一个用于显示不确定进度且带有自定义标签的进度视图。

- **init(_:)**：创建一个用于显示不确定进度且标签由本地化字符串生成的进度视图。

- **init(_:)**：创建一个用于显示不确定进度且标签由字符串生成的进度视图。

## 创建确定进度视图

- **init(_:)**：创建一个用于可视化给定进度实例的进度视图。

- **init(value:total:)**：创建一个用于显示确定进度的进度视图。

- **init(_:value:total:)**：创建一个进度视图，用于显示确定的进度，其标签由字符串生成。

- **init(value:total:label:)**：创建一个进度视图，用于显示确定的进度，并带有自定义标签。

- **init(value:total:label:currentValueLabel:)**：创建一个进度视图，用于显示确定的进度，并带有自定义标签。

## 创建一个跨越特定日期范围的进度视图

- **init(timerInterval:countsDown:)**：创建一个进度视图，用于显示随时间推移而持续变化的进度。

- **init(timerInterval:countsDown:label:)**：创建一个进度视图，用于显示随时间推移而持续变化的进度，并带有描述性标签。

- **init(timerInterval:countsDown:label:currentValueLabel:)**：创建一个进度视图，用于显示随时间推移而持续变化的进度，并带有描述性标签和当前进度标签。

## 初始化器

- **init(_:)**：根据样式配置创建进度视图。

## 指示值

- **Gauge**：显示指定范围内值的视图。

- **gaugeStyle(_:)**：设置此视图中仪表盘的样式。

- **progressViewStyle(_:)**：设置此视图中进度视图的样式。

- **DefaultDateProgressLabel**：日期相关进度视图使用时，当前值标签的默认类型。

- **DefaultButtonLabel**：按钮使用的默认标签。

## 符合以下规范

- 视图


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView
crawled: 2025-12-02T17:27:39Z
---

# ProgressView

**Structure**

A view that shows the progress toward completion of a task.

## Declaration

```swift
struct ProgressView<Label, CurrentValueLabel> where Label : View, CurrentValueLabel : View
```

## Overview

Use a progress view to show that a task is incomplete but advancing toward completion. A progress view can show both determinate (percentage complete) and indeterminate (progressing or not) types of progress.

Create a determinate progress view by initializing a `ProgressView` with a binding to a numeric value that indicates the progress, and a `total` value that represents completion of the task. By default, the progress is `0.0` and the total is `1.0`.

The example below uses the state property `progress` to show progress in a determinate `ProgressView`. The progress view uses its default total of `1.0`, and because `progress` starts with an initial value of `0.5`, the progress view begins half-complete. A “More” button below the progress view allows people to increment the progress in increments of five percent:

```swift
struct LinearProgressDemoView: View {
    @State private var progress = 0.5

    var body: some View {
        VStack {
            ProgressView(value: progress)
            Button("More") { progress += 0.05 }
        }
    }
}
```



To create an indeterminate progress view, use an initializer that doesn’t take a progress value:

```swift
var body: some View {
    ProgressView()
}
```



You can also create a progress view that covers a closed range of [doc://com.apple.documentation/documentation/Foundation/Date] values. As long as the current date is within the range, the progress view automatically updates, filling or depleting the progress view as it nears the end of the range. The following example shows a five-minute timer whose start time is that of the progress view’s initialization:

```swift
struct DateRelativeProgressDemoView: View {
    let workoutDateRange = Date()...Date().addingTimeInterval(5*60)

    var body: some View {
         ProgressView(timerInterval: workoutDateRange) {
             Text("Workout")
         }
    }
}
```



### Styling progress views

You can customize the appearance and interaction of progress views by creating styles that conform to the [ProgressViewStyle](ProgressViewStyle.zh-Hans.md) protocol. To set a specific style for all progress view instances within a view, use the [progressViewStyle(_:)](View/progressViewStyle.zh-Hans.md) modifier. In the following example, a custom style adds a rounded pink border to all progress views within the enclosing [VStack](VStack.zh-Hans.md):

```swift
struct BorderedProgressViews: View {
    var body: some View {
        VStack {
            ProgressView(value: 0.25) { Text("25% progress") }
            ProgressView(value: 0.75) { Text("75% progress") }
        }
        .progressViewStyle(PinkBorderedProgressViewStyle())
    }
}

struct PinkBorderedProgressViewStyle: ProgressViewStyle {
    func makeBody(configuration: Configuration) -> some View {
        ProgressView(configuration)
            .padding(4)
            .border(.pink, width: 3)
            .cornerRadius(4)
    }
}
```



SwiftUI provides two built-in progress view styles, [linear](ProgressViewStyle/linear.zh-Hans.md) and [circular](ProgressViewStyle/circular.zh-Hans.md), as well as an automatic style that defaults to the most appropriate style in the current context. The following example shows a circular progress view that starts at 60 percent completed.

```swift
struct CircularProgressDemoView: View {
    @State private var progress = 0.6

    var body: some View {
        VStack {
            ProgressView(value: progress)
                .progressViewStyle(.circular)
        }
    }
}
```



On platforms other than macOS, the circular style may appear as an indeterminate indicator instead.

## Creating an indeterminate progress view

- **init()**: Creates a progress view for showing indeterminate progress, without a label.
- **init(label:)**: Creates a progress view for showing indeterminate progress that displays a custom label.
- **init(_:)**: Creates a progress view for showing indeterminate progress that generates its label from a localized string.
- **init(_:)**: Creates a progress view for showing indeterminate progress that generates its label from a string.

## Creating a determinate progress view

- **init(_:)**: Creates a progress view for visualizing the given progress instance.
- **init(value:total:)**: Creates a progress view for showing determinate progress.
- **init(_:value:total:)**: Creates a progress view for showing determinate progress that generates its label from a string.
- **init(value:total:label:)**: Creates a progress view for showing determinate progress, with a custom label.
- **init(value:total:label:currentValueLabel:)**: Creates a progress view for showing determinate progress, with a custom label.

## Create a progress view spanning a date range

- **init(timerInterval:countsDown:)**: Creates a progress view for showing continuous progress as time passes.
- **init(timerInterval:countsDown:label:)**: Creates a progress view for showing continuous progress as time passes, with a descriptive label.
- **init(timerInterval:countsDown:label:currentValueLabel:)**: Creates a progress view for showing continuous progress as time passes, with descriptive and current progress labels.

## Initializers

- **init(_:)**: Creates a progress view based on a style configuration.

## Indicating a value

- **Gauge**: A view that shows a value within a range.
- **gaugeStyle(_:)**: Sets the style for gauges within this view.
- **progressViewStyle(_:)**: Sets the style for progress views in this view.
- **DefaultDateProgressLabel**: The default type of the current value label when used by a date-relative progress view.
- **DefaultButtonLabel**: The default label to use for a button.

## Conforms To

- View

