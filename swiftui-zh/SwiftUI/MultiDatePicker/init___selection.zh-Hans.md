---
来源：https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(_:selection:)
抓取时间： 2025-12-01T10:32:21Z
---

# init(_:selection:)

**Initializer**

创建一个实例，用于选择范围不受限制的多个日期。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Set<DateComponents>>)
```

## 参数

- **titleKey**：`self`的本地化标题关键字，描述其目的。
- **selection**：显示和选择的日期值。

## 挑选日期

- **init(selection:label:)**：创建一个实例，用于选择范围不受限制的多个日期。


---
source: https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(_:selection:)
crawled: 2025-12-01T10:32:21Z
---

# init(_:selection:)

**Initializer**

Creates an instance that selects multiple dates with an unbounded range.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<Set<DateComponents>>)
```

## Parameters

- **titleKey**: The key for the localized title of `self`, describing its purpose.
- **selection**: The date values being displayed and selected.

## Picking dates

- **init(selection:label:)**: Creates an instance that selects multiple dates with an unbounded range.

