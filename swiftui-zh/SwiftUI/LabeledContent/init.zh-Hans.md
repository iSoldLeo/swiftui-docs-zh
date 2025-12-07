--- 来源：https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:)

抓取时间：2025-12-01T10:31:37Z

---

# init(_:)

**Initializer**

根据标签内容样式配置创建标签内容。

## 声明

```swift
init(_ configuration: LabeledContentStyleConfiguration)
```

## 参数

- **configuration**：标签内容的属性

## 说明

您可以在 [LabeledContentStyle](../LabeledContentStyle.zh-Hans.md) 的 [makeBody(configuration:)](../LabeledContentStyle/makeBody_configuration.zh-Hans.md) 方法中使用此初始化器来创建标签内容实例。这对于仅修改当前样式的自定义样式非常有用，而不是实现全新的样式。

例如，以下样式会在带标签的内容周围添加红色边框，但其他方面保持当前样式不变：

```swift
struct RedBorderLabeledContentStyle: LabeledContentStyle {
    func makeBody(configuration: Configuration) -> some View {
        LabeledContent(configuration)
            .border(.red)
    }
}
```

## 创建带标签的内容

- **init(_:content:)**：创建一个带标签的视图，该视图的标签由本地化的字符串键生成。

- **init(content:label:)**：创建一个标准的带标签元素，该元素包含一个显示元素值和标签的视图。

- **init(_:value:)**：创建一个带标签的信息视图。

- **init(_:value:format:)**：创建一个带标签的信息视图，该视图由格式化的值生成。


---
source: https://developer.apple.com/documentation/SwiftUI/LabeledContent/init(_:)
crawled: 2025-12-01T10:31:37Z
---

# init(_:)

**Initializer**

Creates labeled content based on a labeled content style configuration.

## Declaration

```swift
init(_ configuration: LabeledContentStyleConfiguration)
```

## Parameters

- **configuration**: The properties of the labeled content

## Discussion

You can use this initializer within the [makeBody(configuration:)](../LabeledContentStyle/makeBody_configuration.zh-Hans.md) method of a [LabeledContentStyle](../LabeledContentStyle.zh-Hans.md) to create a labeled content instance. This is useful for custom styles that only modify the current style, as opposed to implementing a brand new style.

For example, the following style adds a red border around the labeled content, but otherwise preserves the current style:

```swift
struct RedBorderLabeledContentStyle: LabeledContentStyle {
    func makeBody(configuration: Configuration) -> some View {
        LabeledContent(configuration)
            .border(.red)
    }
}
```

## Creating labeled content

- **init(_:content:)**: Creates a labeled view that generates its label from a localized string key.
- **init(content:label:)**: Creates a standard labeled element, with a view that conveys the value of the element and a label.
- **init(_:value:)**: Creates a labeled informational view.
- **init(_:value:format:)**: Creates a labeled informational view from a formatted value.

