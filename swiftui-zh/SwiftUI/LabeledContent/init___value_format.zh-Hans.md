--- 来源：https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:value:format:)

抓取时间：2025-12-01T10:31:37Z

---

# init(_:value:format:)

**Initializer**

根据格式化值创建带标签的信息视图。

## 声明

```swift
init<F>(_ titleKey: LocalizedStringKey, value: F.FormatInput, format: F) where F : FormatStyle, F.FormatInput : Equatable, F.FormatOutput == String
```

## 参数

- **titleKey**：视图本地化标题的键，用于描述视图的用途。

- **value**：要添加标签的值。

- **format**：一种 `F` 类型的格式样式，用于将 `F.FormatInput` 类型的底层值转换为字符串表示形式。

## 讨论

此初始化程序会为您创建一个 [Text](../Text.zh-Hans.md) 标签，并以类似于 [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md) 的方式处理本地化键。有关字符串本地化的更多信息，请参阅 `Text`。

```swift
Form {
    LabeledContent("Age", value: person.age, format: .number)
    LabeledContent("Height", value: person.height,
        format: .measurement(width: .abbreviated))
}
```

## 创建带标签的内容

- **init(_:content:)**：创建一个带标签的视图，该视图根据本地化字符串键生成其标签。

- **init(content:label:)**：创建一个标准的带标签元素，该元素包含一个视图，用于传达元素的值和一个标签。

- **init(_:value:)**：创建带标签的信息视图。

- **init(_:)**：根据标签内容样式配置创建带标签的内容。


---
source: https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:value:format:)
crawled: 2025-12-01T10:31:37Z
---

# init(_:value:format:)

**Initializer**

Creates a labeled informational view from a formatted value.

## Declaration

```swift
init<F>(_ titleKey: LocalizedStringKey, value: F.FormatInput, format: F) where F : FormatStyle, F.FormatInput : Equatable, F.FormatOutput == String
```

## Parameters

- **titleKey**: The key for the view’s localized title, that describes the purpose of the view.
- **value**: The value being labeled.
- **format**: A format style of type `F` to convert the underlying value of type `F.FormatInput` to a string representation.

## Discussion

This initializer creates a [Text](../Text.zh-Hans.md) label on your behalf, and treats the localized key similar to [init(_:tableName:bundle:comment:)](../Text/init___tableName_bundle_comment.zh-Hans.md). See `Text` for more information about localizing strings.

```swift
Form {
    LabeledContent("Age", value: person.age, format: .number)
    LabeledContent("Height", value: person.height,
        format: .measurement(width: .abbreviated))
}
```

## Creating labeled content

- **init(_:content:)**: Creates a labeled view that generates its label from a localized string key.
- **init(content:label:)**: Creates a standard labeled element, with a view that conveys the value of the element and a label.
- **init(_:value:)**: Creates a labeled informational view.
- **init(_:)**: Creates labeled content based on a labeled content style configuration.

