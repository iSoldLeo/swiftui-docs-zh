---
来源：https://developer.apple.com/documentation/SwiftUI/DatePicker/init(_:selection:in:displayedComponents:)
抓取时间：2025-12-03T05:40:36Z
---

# init(_:selection:in:displayedComponents:)

**Initializer**

创建一个实例，选择封闭范围内的`Date`。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Date>, in range: ClosedRange<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date])
```

## 参数

- **titleKey**：`self`的本地化标题关键字，描述其目的。
- **selection**：显示和选择的日期值。
- **range**：可选日期的包含范围。
- **displayedComponents**：用户可以查看和编辑的日期组件。默认为 `[.hourAndMinute, .date]`。在 watchOS 上，如果`.hourAndMinute` 或 `.hourMinuteAndSecond` 与 `.date` 包含在一起，则只显示`.date`。

## 为特定日期创建日期选择器

- **init(selection:in:displayedComponents:label:)**：创建一个实例，选择封闭范围内的`Date`。


---
source: https://developer.apple.com/documentation/SwiftUI/DatePicker/init(_:selection:in:displayedComponents:)
crawled: 2025-12-03T05:40:36Z
---

# init(_:selection:in:displayedComponents:)

**Initializer**

Creates an instance that selects a `Date` in a closed range.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Date>, in range: ClosedRange<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date])
```

## Parameters

- **titleKey**: The key for the localized title of `self`, describing its purpose.
- **selection**: The date value being displayed and selected.
- **range**: The inclusive range of selectable dates.
- **displayedComponents**: The date components that user is able to view and edit. Defaults to `[.hourAndMinute, .date]`. On watchOS, if `.hourAndMinute` or `.hourMinuteAndSecond` are included with `.date`, only `.date` is displayed.

## Creating a date picker for specific dates

- **init(selection:in:displayedComponents:label:)**: Creates an instance that selects a `Date` in a closed range.

