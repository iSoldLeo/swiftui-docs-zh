--- 来源：https://developer.apple.com/documentation/SwiftUI/TextVariantPreference
抓取时间：2025-12-02T17:34:49Z

---

# TextVariantPreference

**Protocol**

用于控制文本视图大小变体的协议。

## 声明

```swift
protocol TextVariantPreference
```

## 类型属性

- **fixed**：默认文本变体首选项。它始终选择最大的可用变体。

- **sizeDependent**：大小相关的首选项允许文本在选择要显示的大小变体时考虑可用空间。

## 调整文本大小

- **textScale(_:isEnabled:)**：对视图中的文本应用文本缩放。

- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。

- **dynamicTypeSize**：当前动态字体大小。

- **DynamicTypeSize**：动态字体大小，用于指定可缩放内容的大小。

- **ScaledMetric**：用于缩放数值的动态属性。

- **FixedTextVariant**：默认文本变体首选项，选择最大可用变体。

- **SizeDependentTextVariant**：大小相关变体首选项允许文本在选择要显示的变体时考虑可用空间。

## 符合规范的类型

- FixedTextVariant

- SizeDependentTextVariant


---
source: https://developer.apple.com/documentation/SwiftUI/TextVariantPreference
crawled: 2025-12-02T17:34:49Z
---

# TextVariantPreference

**Protocol**

A protocol for controlling the size variant of text views.

## Declaration

```swift
protocol TextVariantPreference
```

## Type Properties

- **fixed**: The default text variant preference. It always chooses the largest available variant.
- **sizeDependent**: The size dependent preference allows the text to take the available space into account when choosing the size variant to display.

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **dynamicTypeSize**: The current Dynamic Type size.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

## Conforming Types

- FixedTextVariant
- SizeDependentTextVariant

