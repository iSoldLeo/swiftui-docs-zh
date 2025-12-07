---
来源：https://developer.apple.com/documentation/SwiftUI/Picker/init(_:systemImage:selection:content:)
抓取时间： 2025-12-02T21:55:07Z
---

# init(_:systemImage:selection:content:)

**Initializer**

创建一个拾取器，该拾取器根据本地化的字符串键和系统图像生成标签。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：一个本地化字符串键，用于描述选择选项的目的。
- **systemImage**：要查找的图像资源的名称。
- **selection**：与确定当前所选选项的属性的绑定。
- **content**：包含选项集的视图。

## 讨论

该初始化程序会代表你创建一个 [Text](../Text.zh-Hans.md) 视图，并处理与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似的本地化键。有关字符串本地化的更多信息，请参阅 [Text](../Text.zh-Hans.md)。

## 创建带有图像标签的拾取器

- **init(_:image:selection:content:)**：创建一个拾取器，该拾取器通过本地化字符串键和图像资源生成标签
- **init(_:image:sources:selection:content:)**：创建绑定到绑定集合的拾取器，该拾取器通过字符串和图像资源生成标签。
- **init(_:systemImage:sources:selection:content:)**：创建与绑定集合绑定的拾取器，该拾取器通过字符串生成标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Picker/init(_:systemImage:selection:content:)
crawled: 2025-12-02T21:55:07Z
---

# init(_:systemImage:selection:content:)

**Initializer**

Creates a picker that generates its label from a localized string key and system image.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, selection: Binding<SelectionValue>, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: A localized string key that describes the purpose of selecting an option.
- **systemImage**: The name of the image resource to lookup.
- **selection**: A binding to a property that determines the currently-selected option.
- **content**: A view that contains the set of options.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) view on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See [Text](../Text.zh-Hans.md) for more information about localizing strings.

## Creating a picker with an image label

- **init(_:image:selection:content:)**: Creates a picker that generates its label from a localized string key and image resource
- **init(_:image:sources:selection:content:)**: Creates a picker bound to a collection of bindings that generates its label from a string and image resource.
- **init(_:systemImage:sources:selection:content:)**: Creates a picker bound to a collection of bindings that generates its label from a string.

