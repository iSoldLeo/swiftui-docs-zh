---
来源：https://developer.apple.com/documentation/SwiftUI/DatePicker/init(selection:displayComponents:label:)
抓取时间：2025-12-03T05:40:36Z
---

# init(selection:displayedComponents:label:)

**Initializer**

创建一个实例，用于选择范围不受限制的`Date`。

### 声明

```swift
nonisolated init(selection: Binding<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date], @ViewBuilder label: () -> Label)
```

## 参数

- **selection**：显示和选择的日期值。
- **displayedComponents**：用户可以查看和编辑的日期组件。默认为 `[.hourAndMinute, .date]`。在 watchOS 上，如果`.hourAndMinute` 或 `.hourMinuteAndSecond` 与 `.date` 包含在一起，则只显示`.date`。
- **label**：描述日期使用情况的视图。

## 为任意日期创建日期选择器

- **init(_:selection:displayedComponents:)**：创建一个实例，选择范围不受限制的 `Date`。


---
source: https://developer.apple.com/documentation/SwiftUI/DatePicker/init(selection:displayedComponents:label:)
crawled: 2025-12-03T05:40:36Z
---

# init(selection:displayedComponents:label:)

**Initializer**

Creates an instance that selects a `Date` with an unbounded range.

## Declaration

```swift
nonisolated init(selection: Binding<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date], @ViewBuilder label: () -> Label)
```

## Parameters

- **selection**: The date value being displayed and selected.
- **displayedComponents**: The date components that user is able to view and edit. Defaults to `[.hourAndMinute, .date]`. On watchOS, if `.hourAndMinute` or `.hourMinuteAndSecond` are included with `.date`, only `.date` is displayed.
- **label**: A view that describes the use of the date.

## Creating a date picker for any date

- **init(_:selection:displayedComponents:)**: Creates an instance that selects a `Date` with an unbounded range.

