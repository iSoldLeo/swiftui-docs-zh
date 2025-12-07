---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:image:selection:content:currentValueLabel:)
抓取时间：2025-12-02T21:55:10Z


# init(_:image:selection:content:currentValueLabel:)

**Initializer**

创建一个拾取器，该拾取器接受自定义的当前值标签，并通过本地化的字符串键和图像资源生成标签

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View)
```

## 参数

- **titleKey**：一个本地化字符串键，用于描述选择选项的目的。
- **image**：要查找的图像资源的名称。
- **selection**：与决定当前所选选项的属性的绑定。
- **content**：包含选项集的视图。
- **currentValueLabel**：包含选项集的视图：表示选取器当前值的视图。

## 讨论

该初始化程序会代表您创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:image:selection:content:currentValueLabel:)
crawled: 2025-12-02T21:55:10Z
---

# init(_:image:selection:content:currentValueLabel:)

**Initializer**

Creates a picker that accepts a custom current value label and generates its label from a localized string key and image resource

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, image: ImageResource, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content, @ViewBuilder currentValueLabel: () -> some View)
```

## Parameters

- **titleKey**: A localized string key that describes the purpose of selecting an option.
- **image**: The name of the image resource to lookup.
- **selection**: A binding to a property that determines the currently-selected option.
- **content**: A view that contains the set of options.
- **currentValueLabel**: A view that represents the current value of the picker.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

