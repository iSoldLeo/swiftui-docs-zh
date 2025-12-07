---
来源：https://developer.apple.com/documentation/swiftui/tab/init(_:systemimage:value:content:)
抓取时间：2025-12-02T16:16:18Z
---

# init(_:systemImage:value:content:)

**Initializer**

创建一个标签页，当标签页视图的选择与标签页的值相匹配时，标签页视图就会显示该标签页，该标签页的标签项图像使用系统图像，并带有本地化的字符串关键字标签。

## 声明

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, value: Value, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## 参数

- **titleKey**：标签页的标签项的本地化字符串键标签。
- **systemImage**：选项卡的选项卡项的系统图像。
- **value**：选择此选项卡的`selection` 值。
- **content**：选项卡的视图内容。

## 使用系统符号创建选项卡

- **init(_:systemImage:content:)**：创建一个新标签页，您可以在标签页视图中使用系统图像作为标签页项的图像，以及本地化的字符串关键标签。
- **init(_:systemImage:role:content:)**：创建一个新标签页，您可以在标签页视图中使用该标签页项的系统图像和本地化字符串键标签。
- **init(_:systemImage:value:role:content:)**：创建一个标签页，当标签页视图的选择与标签页的值匹配时，标签页视图会显示该标签页，该标签页的标签页项图像使用系统图像，并带有本地化的字符串关键字标签。


---
source: https://developer.apple.com/documentation/swiftui/tab/init(_:systemimage:value:content:)
crawled: 2025-12-02T16:16:18Z
---

# init(_:systemImage:value:content:)

**Initializer**

Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value using a system image for the tab’s tab item image, with a localized string key label.

## Declaration

```swift
nonisolated init(_ titleKey: LocalizedStringKey, systemImage: String, value: Value, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## Parameters

- **titleKey**: The localized string key label for the tab’s tab item.
- **systemImage**: The system image for the tab’s tab item.
- **value**: The `selection` value which selects this tab.
- **content**: The view content of the tab.

## Creating a tab with system symbol

- **init(_:systemImage:content:)**: Creates a new tab that you can use in a tab view using a system image for the tab item’s image, and a localized string key label.
- **init(_:systemImage:role:content:)**: Creates a new tab that you can use in a tab view using a system image for the tab item’s image, and a localized string key label.
- **init(_:systemImage:value:role:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value using a system image for the tab’s tab item image, with a localized string key label.

