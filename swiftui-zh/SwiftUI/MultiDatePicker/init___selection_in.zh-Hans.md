---
来源：https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(_:selection:in:)
抓取时间：2025-12-01T10:32:22Z
---

# init(_:selection:in:)

**Initializer**

创建一个实例，选择某个起始日期上或之后的多个日期。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Set<DateComponents>>, in bounds: PartialRangeFrom<Date>)
```

## 参数

- **titleKey**：`self`的本地化标题关键字，描述其目的。
- **selection**：显示和选择的日期值。
- **bounds**：从某个可选起始日期开始的开放范围。

## 在一个范围内选择日期

- **init(selection:in:label:)**：创建一个实例，选择某个起始日期上或之后的多个日期。


---
source: https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(_:selection:in:)
crawled: 2025-12-01T10:32:22Z
---

# init(_:selection:in:)

**Initializer**

Creates an instance that selects multiple dates on or after some start date.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Set<DateComponents>>, in bounds: PartialRangeFrom<Date>)
```

## Parameters

- **titleKey**: The key for the localized title of `self`, describing its purpose.
- **selection**: The date values being displayed and selected.
- **bounds**: The open range from some selectable start date.

## Picking dates in a range

- **init(selection:in:label:)**: Creates an instance that selects multiple dates on or after some start date.

