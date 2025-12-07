---
来源：https://developer.apple.com/documentation/SwiftUI/Tab/init(_:systemImage:role:content:)
抓取时间： 2025-12-01T00:43:42Z


# init(_:systemImage:role:content:)

**Initializer**

创建一个新标签页，您可以在标签页视图中使用系统图像作为标签页项的图像，以及本地化的字符串关键标签。

### 声明

```swift
init(_ titleKey: LocalizedStringKey, systemImage: String, role: TabRole?, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## 参数

- **titleKey**：标签页选项卡项的本地化字符串键标签。
- **role**：定义选项卡语义目的的角色。
- **content**：标签页的视图内容：标签页的视图内容。

## 使用系统符号创建标签页

- **init(_:systemImage:content:)**：创建一个新标签页，您可以在标签页视图中使用系统图像作为标签页项的图像，以及本地化的字符串关键标签。
- **init(_:systemImage:value:content:)**：创建一个标签页，当标签页视图的选择与标签页的值匹配时，标签页视图将显示该标签页，该标签页的标签页项图像使用系统图像，关键字标签使用本地化字符串。
- **init(_:systemImage:value:role:content:)**：创建一个标签页，当标签页视图的选择与标签页的值相匹配时，标签页视图将显示该标签页，该标签页的标签页项图像使用系统图像，关键字标签使用本地化字符串。


---
source: https://developer.apple.com/documentation/SwiftUI/Tab/init(_:systemImage:role:content:)
crawled: 2025-12-01T00:43:42Z
---

# init(_:systemImage:role:content:)

**Initializer**

Creates a new tab that you can use in a tab view using a system image for the tab item’s image, and a localized string key label.

## Declaration

```swift
init(_ titleKey: LocalizedStringKey, systemImage: String, role: TabRole?, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## Parameters

- **titleKey**: The localized string key label for the tab’s tab item.
- **role**: The role defining the semantic purpose of the tab.
- **content**: The view content of the tab.

## Creating a tab with system symbol

- **init(_:systemImage:content:)**: Creates a new tab that you can use in a tab view using a system image for the tab item’s image, and a localized string key label.
- **init(_:systemImage:value:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value using a system image for the tab’s tab item image, with a localized string key label.
- **init(_:systemImage:value:role:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value using a system image for the tab’s tab item image, with a localized string key label.

