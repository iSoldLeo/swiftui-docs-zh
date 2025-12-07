---
来源：https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/Transferable/init(text:in:)
抓取时间：2025-12-04T13:20:48Z
---

# init(text:in:)

**Initializer**

创建在 SwiftUI 环境中解释的属性字符串的可转移表示。

## 声明

```swift
init(text: AttributedString, in environment: EnvironmentValues)
```

## 讨论

在将`text` 输出为不同的数据格式时，传输表示法可能会使用给定的`environment` 来解析语义属性值，如将某些颜色或字体转换为具体值。这意味着，根据传输过程中使用的表示法，在这一步骤中可能会丢失一些语义信息。






---
source: https://developer.apple.com/documentation/SwiftUI/AttributedTextFormatting/Transferable/init(text:in:)
crawled: 2025-12-04T13:20:48Z
---

# init(text:in:)

**Initializer**

Create a transferable representation of an attributed string as interpreted in a SwiftUI environment.

## Declaration

```swift
init(text: AttributedString, in environment: EnvironmentValues)
```

## Discussion

When exporting the `text` into different data formats, the transfer representation may use the given `environment` to resolve semantic attribute values, such as certain colors or fonts to concrete values. This means that depending on the representation used during transfer, some semantic information may be lost in that step.





