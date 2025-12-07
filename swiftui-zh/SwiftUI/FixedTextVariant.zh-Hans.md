---
来源： https://developer.apple.com/documentation/SwiftUI/FixedTextVariant
抓取时间： 2025-12-02T17:34:49Z
---

# 固定文本变量

**Structure**

默认文本变量首选项，可选择最大的可用变量。

## 声明

```swift
struct FixedTextVariant
```

## 调整文字大小

- **textScale(_:isEnabled:)**：为视图中的文本应用文本缩放比例。
- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。
- **dynamicTypeSize**：当前动态类型大小。
- **DynamicTypeSize**：动态类型大小，指定可扩展内容的大小。
- **ScaledMetric**：动态属性，用于缩放数值。
- **TextVariantPreference**：用于控制文本视图大小变化的协议。
- **SizeDependentTextVariant**：尺寸相关变量首选项允许文本在选择要显示的变量时将可用空间考虑在内。

## 符合

- 可发送
- 可发送元类型
- 文本变量首选项


---
source: https://developer.apple.com/documentation/SwiftUI/FixedTextVariant
crawled: 2025-12-02T17:34:49Z
---

# FixedTextVariant

**Structure**

The default text variant preference that chooses the largest available variant.

## Declaration

```swift
struct FixedTextVariant
```

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **dynamicTypeSize**: The current Dynamic Type size.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

## Conforms To

- Sendable
- SendableMetatype
- TextVariantPreference

