---
来源：https://developer.apple.com/documentation/SwiftUI/DatePicker/init(selection:in:displayComponents:label:)
抓取时间： 2025-12-03T05:40:37Z
---

# init(selection:in:displayedComponents:label:)

**Initializer**

创建一个实例，选择封闭范围内的`Date`。

### 声明

```swift
nonisolated init(selection: Binding<Date>, in range: ClosedRange<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date], @ViewBuilder label: () -> Label)
```

## 参数

- **selection**：显示和选择的日期值。
- **range**：可选日期的包含范围。
- **displayedComponents**：用户可以查看和编辑的日期组件。默认为 `[.hourAndMinute, .date]`。在 watchOS 上，如果`.hourAndMinute` 或 `.hourMinuteAndSecond` 与 `.date` 包含在一起，则只显示`.date`。
- **label**：描述日期使用情况的视图。

## 为特定日期创建日期选择器

- **init(_:selection:in:displayedComponents:)**：创建一个在封闭范围内选择`Date` 的实例。


---
source: https://developer.apple.com/documentation/SwiftUI/DatePicker/init(selection:in:displayedComponents:label:)
crawled: 2025-12-03T05:40:37Z
---

# init(selection:in:displayedComponents:label:)

**Initializer**

Creates an instance that selects a `Date` in a closed range.

## Declaration

```swift
nonisolated init(selection: Binding<Date>, in range: ClosedRange<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date], @ViewBuilder label: () -> Label)
```

## Parameters

- **selection**: The date value being displayed and selected.
- **range**: The inclusive range of selectable dates.
- **displayedComponents**: The date components that user is able to view and edit. Defaults to `[.hourAndMinute, .date]`. On watchOS, if `.hourAndMinute` or `.hourMinuteAndSecond` are included with `.date`, only `.date` is displayed.
- **label**: A view that describes the use of the date.

## Creating a date picker for specific dates

- **init(_:selection:in:displayedComponents:)**: Creates an instance that selects a `Date` in a closed range.

