--- 来源：https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(content:label:)

抓取时间：2025-12-03T05:42:26Z

---

# init(content:label:)

**Initializer**

创建一个标准的标签元素，该元素包含一个显示元素值的视图和一个标签。

## 声明

```swift
nonisolated init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## 参数

- **content**：显示生成的标签元素值的视图。

- **label**：描述结果用途的标签。

## 创建标签内容

- **init(_:content:)**：创建一个标签视图，该视图根据本地化的字符串键生成标签。

- **init(_:value:)**：创建带标签的信息视图。

- **init(_:value:format:)**：根据格式化值创建带标签的信息视图。

- **init(_:)**：根据标签内容样式配置创建带标签的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(content:label:)
crawled: 2025-12-03T05:42:26Z
---

# init(content:label:)

**Initializer**

Creates a standard labeled element, with a view that conveys the value of the element and a label.

## Declaration

```swift
nonisolated init(@ViewBuilder content: () -> Content, @ViewBuilder label: () -> Label)
```

## Parameters

- **content**: The view that conveys the value of the resulting labeled element.
- **label**: The label that describes the purpose of the result.

## Creating labeled content

- **init(_:content:)**: Creates a labeled view that generates its label from a localized string key.
- **init(_:value:)**: Creates a labeled informational view.
- **init(_:value:format:)**: Creates a labeled informational view from a formatted value.
- **init(_:)**: Creates labeled content based on a labeled content style configuration.

