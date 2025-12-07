---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(selection:label:content:)
抓取时间： 2025-12-01T02:45:59Z
---

# init(selection:label:content:)

**Initializer**

创建显示自定义标签的选取器。

## 声明

```swift
nonisolated init(selection: Binding<SelectionValue>, label: Label, @ViewBuilder content: () -> Content)
```

## 参数

- **selection**：与属性的绑定，该属性决定当前选择的选项。
- **label**：描述选择选项目的的视图。
- **content**：包含选项集的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(selection:label:content:)
crawled: 2025-12-01T02:45:59Z
---

# init(selection:label:content:)

**Initializer**

Creates a picker that displays a custom label.

## Declaration

```swift
nonisolated init(selection: Binding<SelectionValue>, label: Label, @ViewBuilder content: () -> Content)
```

## Parameters

- **selection**: A binding to a property that determines the currently-selected option.
- **label**: A view that describes the purpose of selecting an option.
- **content**: A view that contains the set of options.

