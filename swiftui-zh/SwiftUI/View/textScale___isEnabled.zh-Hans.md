--- 来源：https://developer.apple.com/documentation/SwiftUI/View/textScale(_:isEnabled:)

抓取时间：2025-11-30T21:19:52Z

---

# textScale(_:isEnabled:)

**实例方法**

为视图中的文本应用缩放比例。

## 声明

```swift
nonisolated func textScale(_ scale: Text.Scale, isEnabled: Bool = true) -> some View

```

## 参数

- **scale**：要应用的文本缩放比例。

- **isEnabled**：如果为 true，则应用文本缩放比例；否则，文本缩放比例保持不变。

## 返回值

应用了指定文本缩放比例的视图。

## 调整文本大小

- **dynamicTypeSize(_:)**：将视图中的动态类型大小设置为给定值。

- **dynamicTypeSize**：当前动态字体大小。

- **DynamicTypeSize**：动态字体大小，用于指定可缩放内容的大小。

- **ScaledMetric**：用于缩放数值的动态属性。

- **TextVariantPreference**：用于控制文本视图大小变体的协议。

- **FixedTextVariant**：默认文本变体首选项，选择最大可用变体。

- **SizeDependentTextVariant**：大小相关的变体首选项，允许文本在选择要显示的变体时考虑可用空间。


---
source: https://developer.apple.com/documentation/SwiftUI/View/textScale(_:isEnabled:)
crawled: 2025-11-30T21:19:52Z
---

# textScale(_:isEnabled:)

**Instance Method**

Applies a text scale to text in the view.

## Declaration

```swift
nonisolated func textScale(_ scale: Text.Scale, isEnabled: Bool = true) -> some View

```

## Parameters

- **scale**: The text scale to apply.
- **isEnabled**: If true the text scale is applied; otherwise text scale is unchanged.

## Return Value

A view with the specified text scale applied.

## Adjusting text size

- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **dynamicTypeSize**: The current Dynamic Type size.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

