--- 来源：https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)

抓取时间：2025-12-03T05:43:51Z

---

# init(_:)

**Initializer**

根据样式配置创建进度视图。

## 声明

```swift
nonisolated init(_ configuration: ProgressViewStyleConfiguration) where Label == ProgressViewStyleConfiguration.Label, CurrentValueLabel == ProgressViewStyleConfiguration.CurrentValueLabel
```

## 讨论

您可以在 [ProgressViewStyle](../ProgressViewStyle.zh-Hans.md) 的 [makeBody(configuration:)](../ProgressViewStyle/makeBody_configuration.zh-Hans.md) 方法中使用此初始化器来创建样式化的进度视图实例。这对于仅修改当前进度视图样式的自定义进度视图样式非常有用，而不是实现全新的样式。由于此样式修饰符无法知道当前样式如何表示进度，因此请避免对视图的内容（例如是否使用条形或其他形状）做出假设。

以下示例展示了一种样式，它为进度视图添加圆角粉色边框，但除此之外，进度视图保持其现有样式不变：

```swift
struct PinkBorderedProgressViewStyle: ProgressViewStyle {
    func makeBody(configuration: Configuration) -> some View {
        ProgressView(configuration)
            .padding(4)
            .border(.pink, width: 3)
            .cornerRadius(4)
    }
}
```


---
source: https://developer.apple.com/documentation/SwiftUI/ProgressView/init(_:)
crawled: 2025-12-03T05:43:51Z
---

# init(_:)

**Initializer**

Creates a progress view based on a style configuration.

## Declaration

```swift
nonisolated init(_ configuration: ProgressViewStyleConfiguration) where Label == ProgressViewStyleConfiguration.Label, CurrentValueLabel == ProgressViewStyleConfiguration.CurrentValueLabel
```

## Discussion

You can use this initializer within the [makeBody(configuration:)](../ProgressViewStyle/makeBody_configuration.zh-Hans.md) method of a [ProgressViewStyle](../ProgressViewStyle.zh-Hans.md) to create an instance of the styled progress view. This is useful for custom progress view styles that only modify the current progress view style, as opposed to implementing a brand new style. Because this modifier style can’t know how the current style represents progress, avoid making assumptions about the view’s contents, such as whether it uses bars or other shapes.

The following example shows a style that adds a rounded pink border to a progress view, but otherwise preserves the progress view’s current style:

```swift
struct PinkBorderedProgressViewStyle: ProgressViewStyle {
    func makeBody(configuration: Configuration) -> some View {
        ProgressView(configuration)
            .padding(4)
            .border(.pink, width: 3)
            .cornerRadius(4)
    }
}
```





