---
来源： https://developer.apple.com/documentation/SwiftUI/Tab/init(_:image:content:)
抓取时间： 2025-12-01T00:43:44Z
---

# init(_:image:content:)

**Initializer**

创建一个新标签页，可在标签页视图中使用，并带有本地化的字符串关键字标签。

## 声明

```swift
init(_ titleKey: LocalizedStringKey, image: String, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## 参数

- **titleKey**：标签页选项卡项的本地化字符串键标签。
- **image**：选项卡的选项卡项的图像。
- **content**：选项卡的视图内容。

## 创建带图片的标签页

- **init(_:image:value:content:)**：创建一个标签页，当标签页视图的选择与标签页的值相匹配时，标签页视图会显示该标签页，并带有本地化的字符串关键字标签。
- **init(_:image:role:content:)**：创建一个新标签页，可在标签页视图中使用，并带有本地化字符串键标签。
- **init(_:image:value:role:content:)**：创建一个选项卡，当选项卡视图的选择与该选项卡的值匹配时，该选项卡视图将显示该选项卡，并带有本地化字符串关键字标签。


---
source: https://developer.apple.com/documentation/SwiftUI/Tab/init(_:image:content:)
crawled: 2025-12-01T00:43:44Z
---

# init(_:image:content:)

**Initializer**

Creates a new tab that you can use in a tab view, with a localized string key label.

## Declaration

```swift
init(_ titleKey: LocalizedStringKey, image: String, @ViewBuilder content: () -> Content) where Label == DefaultTabLabel
```

## Parameters

- **titleKey**: The localized string key label for the tab’s tab item.
- **image**: The image for the tab’s tab item.
- **content**: The view content of the tab.

## Creating a tab with image

- **init(_:image:value:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value, with a localized string key label.
- **init(_:image:role:content:)**: Creates a new tab that you can use in a tab view, with a localized string key label.
- **init(_:image:value:role:content:)**: Creates a tab that the tab view presents when the tab view’s selection matches the tab’s value, with a localized string key label.

