--- 来源：https://developer.apple.com/documentation/SwiftUI/View/help(_:)

抓取时间：2025-12-02T17:32:43Z

---

# help(_:)

**实例方法**

使用您提供的文本视图向视图添加帮助文本。

## 声明

```swift
nonisolated func help(_ text: Text) -> some View

```

## 参数

- **text**：要用作帮助的视图。[Text](../Text.zh-Hans.md)

## 说明

向视图添加帮助会配置视图的辅助功能提示及其在 macOS 或 VisionOS 中的帮助标签（也称为“工具提示”）。有关使用帮助标签的更多信息，请参阅《人机界面指南》。[doc://com.apple.documentation/design/Human-Interface-Guidelines/offering-help]

```swift
Slider("Opacity", value: $selectedShape.opacity)
    .help(Text("Adjust the opacity of the selected \(selectedShape.name)"))
```


---
source: https://developer.apple.com/documentation/SwiftUI/View/help(_:)
crawled: 2025-12-02T17:32:43Z
---

# help(_:)

**Instance Method**

Adds help text to a view using a text view that you provide.

## Declaration

```swift
nonisolated func help(_ text: Text) -> some View

```

## Parameters

- **text**: The [Text](../Text.zh-Hans.md) view to use as help.

## Discussion

Adding help to a view configures the view’s accessibility hint and its help tag (also called a *tooltip*) in macOS or visionOS. For more information on using help tags, see [doc://com.apple.documentation/design/Human-Interface-Guidelines/offering-help] in the Human Interface Guidelines.

```swift
Slider("Opacity", value: $selectedShape.opacity)
    .help(Text("Adjust the opacity of the selected \(selectedShape.name)"))
```

