--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/textScale(_:isEnabled:)

抓取时间：2025-12-01T02:39:25Z

---

# textScale(_:isEnabled:)

**实例方法**

为文本应用缩放比例。

## 声明

```swift
func textScale(_ scale: Text.Scale, isEnabled: Bool = true) -> Text
```

## 参数

- **scale**：要应用的文本缩放比例。

- **isEnabled**：如果为 true，则应用文本缩放比例；否则，文本缩放比例保持不变。

## 返回值

应用指定缩放比例后的文本。

## 将文本适配到可用空间

- **Text.Scale**：定义文本缩放比例

- **Text.TruncationMode**：当文本行过长而无法容纳在可用空间时，应用的截断类型。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/textScale(_:isEnabled:)
crawled: 2025-12-01T02:39:25Z
---

# textScale(_:isEnabled:)

**Instance Method**

Applies a text scale to the text.

## Declaration

```swift
func textScale(_ scale: Text.Scale, isEnabled: Bool = true) -> Text
```

## Parameters

- **scale**: The text scale to apply.
- **isEnabled**: If true the text scale is applied; otherwise text scale is unchanged.

## Return Value

Text with the specified scale applied.

## Fitting text into available space

- **Text.Scale**: Defines text scales
- **Text.TruncationMode**: The type of truncation to apply to a line of text when it’s too long to fit in the available space.

