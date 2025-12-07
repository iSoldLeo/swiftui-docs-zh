---
来源： https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibility(inputLabels:)
抓取时间： 2025-12-02T17:46:40Z
---

# accessibility(inputLabels:)

**实例方法**

设置备用输入标签，以便用户识别视图。

## 声明

```swift
nonisolated func accessibility(inputLabels: [Text]) -> ModifiedContent<Content, Modifier>
```

## 参数

- **inputLabels**：用于输入标签的[Text](../Text.zh-Hans.md) 元素数组。

## 讨论

按重要性降序提供标签。语音控制和全键盘访问使用输入标签。




---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/accessibility(inputLabels:)
crawled: 2025-12-02T17:46:40Z
---

# accessibility(inputLabels:)

**Instance Method**

Sets alternate input labels with which users identify a view.

## Declaration

```swift
nonisolated func accessibility(inputLabels: [Text]) -> ModifiedContent<Content, Modifier>
```

## Parameters

- **inputLabels**: An array of [Text](../Text.zh-Hans.md) elements to use as input labels.

## Discussion

Provide labels in descending order of importance. Voice Control and Full Keyboard Access use the input labels.



