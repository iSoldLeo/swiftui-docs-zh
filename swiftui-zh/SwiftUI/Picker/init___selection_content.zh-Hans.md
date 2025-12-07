---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(_:selection:content:)
抓取时间： 2025-12-02T21:55:03Z
---

# init(_:selection:content:)

**Initializer**

创建一个选取器，该选取器根据本地化的字符串键生成标签。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：一个本地化字符串键，用于描述选择选项的目的。
- **selection**：与属性的绑定，该属性决定当前选择的选项。
- **content**：包含选项集的视图。

## 讨论

该初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建选取器

- **init(selection:content:label:)**：创建显示自定义标签的选取器。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:selection:content:)
crawled: 2025-12-02T21:55:03Z
---

# init(_:selection:content:)

**Initializer**

Creates a picker that generates its label from a localized string key.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: A localized string key that describes the purpose of selecting an option.
- **selection**: A binding to a property that determines the currently-selected option.
- **content**: A view that contains the set of options.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Creating a picker

- **init(selection:content:label:)**: Creates a picker that displays a custom label.

