---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(selection:content:label:)
抓取时间： 2025-12-01T02:45:55Z
---

# init(selection:content:label:)

**Initializer**

创建显示自定义标签的选取器。

## 声明

```swift
nonisolated init(selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **selection**：与属性的绑定，该属性决定当前选择的选项。
- **content**：包含选项集的视图。
- **label**：包含选项集的视图：描述选择某个选项的目的的视图。

## 创建选取器

- **init(_:selection:content:)**：创建一个选取器，该选取器的标签由本地化的字符串键生成。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(selection:content:label:)
crawled: 2025-12-01T02:45:55Z
---

# init(selection:content:label:)

**Initializer**

Creates a picker that displays a custom label.

## Declaration

```swift
nonisolated init(selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **selection**: A binding to a property that determines the currently-selected option.
- **content**: A view that contains the set of options.
- **label**: A view that describes the purpose of selecting an option.

## Creating a picker

- **init(_:selection:content:)**: Creates a picker that generates its label from a localized string key.

