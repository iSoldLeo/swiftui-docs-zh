---
来源：https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(selection:label:)
抓取时间： 2025-12-03T05:43:10Z
---

# init(selection:label:)

**Initializer**

创建一个实例，用于选择范围不受限制的多个日期。

### 声明

```swift
nonisolated init(selection: Binding<Set<DateComponents>>, @ViewBuilder label: () -> Label)
```

## 参数

- **selection**：显示和选择的日期值。
- **label**：描述日期用途的视图。

## 挑选日期

- **init(_:selection:)**：创建一个实例，选择范围不受限制的多个日期。


---
source: https://developer.apple.com/documentation/SwiftUI/MultiDatePicker/init(selection:label:)
crawled: 2025-12-03T05:43:10Z
---

# init(selection:label:)

**Initializer**

Creates an instance that selects multiple dates with an unbounded range.

## Declaration

```swift
nonisolated init(selection: Binding<Set<DateComponents>>, @ViewBuilder label: () -> Label)
```

## Parameters

- **selection**: The date values being displayed and selected.
- **label**: A view that describes the use of the dates.

## Picking dates

- **init(_:selection:)**: Creates an instance that selects multiple dates with an unbounded range.

