--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityRepresentation(representation:)

抓取时间：2025-12-02T16:49:02Z

---

# accessibilityRepresentation(representation:)

**实例方法**

将此视图的一个或多个辅助功能元素替换为新的辅助功能元素。

## 声明

```swift
nonisolated func accessibilityRepresentation<V>(@ViewBuilder representation: () -> V) -> some View where V : View

```

## 参数

- **representation**：辅助功能系统用于生成辅助功能元素的隐藏视图。

## 说明

您可以使用自定义样式使控件具有辅助功能。例如，您创建的自定义 [ToggleStyle](../ToggleStyle.zh-Hans.md) 会自动继承 [Toggle](../Toggle.zh-Hans.md) 的辅助功能。当无法使用父视图的辅助功能元素时，请改用 `accessibilityRepresentation(representation:)` 修饰符。此修饰符会将默认的辅助功能元素替换为您提供的其他辅助功能元素。您可以使用合成的、非视觉的辅助功能元素来表示视图显示的内容。

以下示例通过使用 [Slider](../Slider.zh-Hans.md) 显式定义步长增量的表示方式，使自定义可调节控件具有可访问性：

```swift
var body: some View {
    VStack {
        SliderTrack(...) // Custom slider implementation.
    }
    .accessibilityRepresentation {
        Slider(value: $value, in: 0...100) {
            Text("Label")
        }
    }
}
```

SwiftUI 会隐藏您在 `representation` 闭包中提供的视图，并使其不可交互。框架仅使用它来生成辅助功能元素。

## 创建辅助功能元素

- **accessibilityElement(children:)**：创建一个新的辅助功能元素，或修改现有辅助功能元素的 [AccessibilityChildBehavior](../AccessibilityChildBehavior.zh-Hans.md)。

- **accessibilityChildren(children:)**：将现有辅助功能元素的子元素替换为一个或多个新的合成辅助功能元素。

- **AccessibilityChildBehavior**：定义新父元素的子元素的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityRepresentation(representation:)
crawled: 2025-12-02T16:49:02Z
---

# accessibilityRepresentation(representation:)

**Instance Method**

Replaces one or more accessibility elements for this view with new accessibility elements.

## Declaration

```swift
nonisolated func accessibilityRepresentation<V>(@ViewBuilder representation: () -> V) -> some View where V : View

```

## Parameters

- **representation**: A hidden view that the accessibility system uses to generate accessibility elements.

## Discussion

You can make controls accessible by using a custom style. For example, a custom [ToggleStyle](../ToggleStyle.zh-Hans.md) that you create inherits the accessibility features of [Toggle](../Toggle.zh-Hans.md) automatically. When you can’t use the parent view’s accessibility elements, use the `accessibilityRepresentation(representation:)` modifier instead. This modifier replaces default accessibility elements with different accessibility elements that you provide. You use synthetic, non-visual accessibility elements to represent what the view displays.

The example below makes a custom adjustable control accessible by explicitly defining the representation of its step increments using a [Slider](../Slider.zh-Hans.md):

```swift
var body: some View {
    VStack {
        SliderTrack(...) // Custom slider implementation.
    }
    .accessibilityRepresentation {
        Slider(value: $value, in: 0...100) {
            Text("Label")
        }
    }
}
```

SwiftUI hides the view that you provide in the `representation` closure and makes it non-interactive. The framework uses it only to generate accessibility elements.

## Creating accessible elements

- **accessibilityElement(children:)**: Creates a new accessibility element, or modifies the [AccessibilityChildBehavior](../AccessibilityChildBehavior.zh-Hans.md) of the existing accessibility element.
- **accessibilityChildren(children:)**: Replaces the existing accessibility element’s children with one or more new synthetic accessibility elements.
- **AccessibilityChildBehavior**: Defines the behavior for the child elements of the new parent element.

