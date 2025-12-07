---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(_:selection:content:currentValueLabel:)
抓取时间：2025-12-01T02:46:01Z


# init(_:selection:content:currentValueLabel:)

**Initializer**

创建一个选取器，该选取器通过本地化字符串键生成标签，并接受自定义的当前值标签。

### 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View)
```

## 参数

- **titleKey**：一个本地化字符串键，用于描述选择选项的目的。
- **selection**：与属性的绑定，该属性决定当前选择的选项。
- **content**：包含选项集的视图。
- **currentValueLabel**：包含选项集的视图：表示选取器当前值的视图。

## 讨论

该初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:selection:content:currentValueLabel:)
crawled: 2025-12-01T02:46:01Z
---

# init(_:selection:content:currentValueLabel:)

**Initializer**

Creates a picker that generates its label from a localized string key and accepts a custom current value label.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View)
```

## Parameters

- **titleKey**: A localized string key that describes the purpose of selecting an option.
- **selection**: A binding to a property that determines the currently-selected option.
- **content**: A view that contains the set of options.
- **currentValueLabel**: A view that represents the current value of the picker.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

