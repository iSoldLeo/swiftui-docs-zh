---
来源：https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(selection:in:label:)
抓取时间： 2025-12-01T10:32:23Z
---

# init(selection:in:label:)

**Initializer**

创建一个实例，选择某个起始日期当天或之后的多个日期。

## 声明

```swift
nonisolated init(selection: Binding<Set<DateComponents>>, in bounds: PartialRangeFrom<Date>, @ViewBuilder label: () -> Label)
```

## 参数

- **selection**：显示和选择的日期值。
- **bounds**：从某个可选起始日期开始的开放范围。
- **label**：描述日期使用情况的视图。

## 在一个范围内选择日期

- **init(_:selection:in:)**：创建一个实例，选择某个起始日期或之后的多个日期。


---
source: https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(selection:in:label:)
crawled: 2025-12-01T10:32:23Z
---

# init(selection:in:label:)

**Initializer**

Creates an instance that selects multiple dates on or after some start date.

## Declaration

```swift
nonisolated init(selection: Binding<Set<DateComponents>>, in bounds: PartialRangeFrom<Date>, @ViewBuilder label: () -> Label)
```

## Parameters

- **selection**: The date values being displayed and selected.
- **bounds**: The open range from some selectable start date.
- **label**: A view that describes the use of the dates.

## Picking dates in a range

- **init(_:selection:in:)**: Creates an instance that selects multiple dates on or after some start date.

