---
来源： https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dynamicTypeSize
抓取时间： 2025-12-02T17:34:46Z
---

# 动态类型大小

**实例属性**

当前动态类型的大小。

## 声明

```swift
var dynamicTypeSize: DynamicTypeSize { get set }
```

## 讨论

该值随用户选择的动态类型大小的变化而变化。默认值取决于设备。

在限制动态类型大小时，请考虑是否适合使用 [accessibilityShowsLargeContentViewer()](../View/accessibilityShowsLargeContentViewer.zh-Hans.md) 添加大型内容视图。

在 macOS 上，用户无法更改此值，也不会影响文本大小。

## 调整文本大小

- **textScale(_:isEnabled:)**：为视图中的文本应用文本缩放比例。
- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。
- **DynamicTypeSize**：动态类型大小，用于指定可扩展内容的大小。
- **ScaledMetric**：动态属性，用于缩放数值。
- **TextVariantPreference**：用于控制文本视图大小变化的协议。
- **FixedTextVariant**：选择最大可用变量的默认文本变量首选项。
- **SizeDependentTextVariant**：取决于大小的变体首选项允许文本在选择要显示的变体时将可用空间考虑在内。


---
source: https://developer.apple.com/documentation/SwiftUI/EnvironmentValues/dynamicTypeSize
crawled: 2025-12-02T17:34:46Z
---

# dynamicTypeSize

**Instance Property**

The current Dynamic Type size.

## Declaration

```swift
var dynamicTypeSize: DynamicTypeSize { get set }
```

## Discussion

This value changes as the user’s chosen Dynamic Type size changes. The default value is device-dependent.

When limiting the Dynamic Type size, consider if adding a large content view with [accessibilityShowsLargeContentViewer()](../View/accessibilityShowsLargeContentViewer.zh-Hans.md) would be appropriate.

On macOS, this value cannot be changed by users and does not affect the text size.

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

