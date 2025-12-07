--- 来源：https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:content:)

抓取时间：2025-12-03T05:42:26Z

---

# init(_:content:)

**Initializer**

创建一个标签视图，该视图的标签由本地化字符串键生成。

## 声明

```swift
init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content)
```

## 参数

- **titleKey**：视图本地化标题的键，用于描述视图的用途。

- **content**：要标记的值内容。

## 说明

此初始化器会为您创建一个 [Text](../Text.zh-Hans.md) 标签，并且处理本地化键的方式与 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 类似。有关字符串本地化的更多信息，请参阅 `Text`。

## 创建带标签的内容

- **init(content:label:)**：创建一个标准带标签的元素，该元素包含一个显示元素值和标签的视图。

- **init(_:value:)**：创建一个带标签的信息视图。

- **init(_:value:format:)**：根据格式化值创建带标签的信息视图。

- **init(_:)**：根据带标签的内容样式配置创建带标签的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:content:)
crawled: 2025-12-03T05:42:26Z
---

# init(_:content:)

**Initializer**

Creates a labeled view that generates its label from a localized string key.

## Declaration

```swift
init(_ titleKey: LocalizedStringKey, @ViewBuilder content: () -> Content)
```

## Parameters

- **titleKey**: The key for the view’s localized title, that describes the purpose of the view.
- **content**: The value content being labeled.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) label on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See `Text` for more information about localizing strings.

## Creating labeled content

- **init(content:label:)**: Creates a standard labeled element, with a view that conveys the value of the element and a label.
- **init(_:value:)**: Creates a labeled informational view.
- **init(_:value:format:)**: Creates a labeled informational view from a formatted value.
- **init(_:)**: Creates labeled content based on a labeled content style configuration.

