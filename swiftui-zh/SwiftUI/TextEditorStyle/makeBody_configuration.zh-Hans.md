--- 来源：https://developer.apple.com/documentation/SwiftUI/TextEditorStyle/makeBody(configuration:)

抓取时间：2025-12-03T06:10:42Z

---

# makeBody(configuration:)

**实例方法**

创建一个表示文本编辑器主体的视图。

## 声明

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## 参数

- **configuration**：文本编辑器的属性。

## 说明

系统会针对视图层次结构中每个 [TextEditor](../TextEditor.zh-Hans.md) 实例调用此方法，前提是该实例的当前文本编辑器样式为该样式。

## 创建自定义样式

- **TextEditorStyle.Configuration**：文本编辑器的属性。

- **Body**：表示文本编辑器主体的视图。


---
source: https://developer.apple.com/documentation/SwiftUI/TextEditorStyle/makeBody(configuration:)
crawled: 2025-12-03T06:10:42Z
---

# makeBody(configuration:)

**Instance Method**

Creates a view that represents the body of a text editor.

## Declaration

```swift
@ViewBuilder @MainActor @preconcurrency func makeBody(configuration: Self.Configuration) -> Self.Body
```

## Parameters

- **configuration**: The properties of the text editor.

## Discussion

The system calls this method for each [TextEditor](../TextEditor.zh-Hans.md) instance in a view hierarchy where this style is the current text editor style.

## Creating custom styles

- **TextEditorStyle.Configuration**: The properties of a text editor.
- **Body**: A view that represents the body of a text editor.

