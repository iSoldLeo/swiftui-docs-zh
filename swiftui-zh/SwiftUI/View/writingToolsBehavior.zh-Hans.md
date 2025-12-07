--- 来源：https://developer.apple.com/documentation/SwiftUI/View/writingToolsBehavior(_:)

抓取时间：2025-11-30T21:11:35Z

---

# writingToolsBehavior(_:)

**实例方法**

指定环境中文本和文本输入的写作工具行为。

## 声明

```swift
@MainActor @preconcurrency func writingToolsBehavior(_ behavior: WritingToolsBehavior) -> some View

```

## 参数

- **behavior**：环境中文本和文本输入的写作工具行为。

## 返回值

一个优先使用指定写作工具行为的视图。

## 说明

使用此视图修饰符可以自定义或禁用 [Text](../Text.zh-Hans.md)（可选时）、[TextField](../TextField.zh-Hans.md) 和 [TextEditor](../TextEditor.zh-Hans.md) 视图的写作工具编辑体验。

## 配置写作工具的行为

- **WritingToolsBehavior**：写作工具的文本编辑和文本输入体验。


---
source: https://developer.apple.com/documentation/SwiftUI/View/writingToolsBehavior(_:)
crawled: 2025-11-30T21:11:35Z
---

# writingToolsBehavior(_:)

**Instance Method**

Specifies the Writing Tools behavior for text and text input in the environment.

## Declaration

```swift
@MainActor @preconcurrency func writingToolsBehavior(_ behavior: WritingToolsBehavior) -> some View

```

## Parameters

- **behavior**: The Writing Tools behavior for text and text input in the environment.

## Return Value

A view preferring the specified Writing Tools behavior.

## Discussion

Use this view modifier to customize or disable the Writing Tools editing experience for [Text](../Text.zh-Hans.md) (when selectable), [TextField](../TextField.zh-Hans.md), and [TextEditor](../TextEditor.zh-Hans.md) views.

## Configuring the Writing Tools behavior

- **WritingToolsBehavior**: The Writing Tools editing experience for text and text input.

