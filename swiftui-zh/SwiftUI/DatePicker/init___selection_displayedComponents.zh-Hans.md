---
来源：https://developer.apple.com/documentation/SwiftUI/DatePicker/init(_:selection:displayedComponents:)
抓取时间： 2025-12-01T10:29:43Z
---

# init(_:selection:displayedComponents:)

**Initializer**

创建一个实例，用于选择范围不受限制的`Date`。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date])
```

## 参数

- **titleKey**：`self`的本地化标题键，描述其目的。
- **selection**：显示和选择的日期值。
- **displayedComponents**：用户可以查看和编辑的日期组件。默认为 `[.hourAndMinute, .date]`。在 watchOS 上，如果`.hourAndMinute` 或 `.hourMinuteAndSecond` 与 `.date` 包含在一起，则只显示`.date`。

## 为任意日期创建日期选择器

- **init(selection:displayedComponents:label:)**：创建一个实例，选择范围不受限制的`Date`。


---
source: https://developer.apple.com/documentation/SwiftUI/DatePicker/init(_:selection:displayedComponents:)
crawled: 2025-12-01T10:29:43Z
---

# init(_:selection:displayedComponents:)

**Initializer**

Creates an instance that selects a `Date` with an unbounded range.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Date>, displayedComponents: DatePicker<Label>.Components = [.hourAndMinute, .date])
```

## Parameters

- **titleKey**: The key for the localized title of `self`, describing its purpose.
- **selection**: The date value being displayed and selected.
- **displayedComponents**: The date components that user is able to view and edit. Defaults to `[.hourAndMinute, .date]`. On watchOS, if `.hourAndMinute` or `.hourMinuteAndSecond` are included with `.date`, only `.date` is displayed.

## Creating a date picker for any date

- **init(selection:displayedComponents:label:)**: Creates an instance that selects a `Date` with an unbounded range.

