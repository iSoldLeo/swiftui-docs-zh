---
来源： https://developer.apple.com/documentation/SwiftUI/SizeDependentTextVariant
抓取时间： 2025-12-02T17:34:50Z
---

# 大小取决于文本变量

**Structure**

尺寸相关变量首选项允许文本在选择要显示的变量时考虑可用空间。

## 声明

```swift
struct SizeDependentTextVariant
```

## 调整文字大小

- **textScale(_:isEnabled:)**：为视图中的文本应用文本缩放比例。
- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。
- **dynamicTypeSize**：当前动态类型大小。
- **DynamicTypeSize**：动态类型大小，指定可扩展内容的大小。
- **ScaledMetric**：动态属性，用于缩放数值。
- **TextVariantPreference**：用于控制文本视图大小变化的协议。
- **FixedTextVariant**：选择最大可用变量的默认文本变量首选项。

## 符合

- 可发送
- 可发送元类型
- 文本变量首选项


---
source: https://developer.apple.com/documentation/SwiftUI/SizeDependentTextVariant
crawled: 2025-12-02T17:34:50Z
---

# SizeDependentTextVariant

**Structure**

The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

## Declaration

```swift
struct SizeDependentTextVariant
```

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **dynamicTypeSize**: The current Dynamic Type size.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.

## Conforms To

- Sendable
- SendableMetatype
- TextVariantPreference

