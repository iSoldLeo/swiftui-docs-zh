--- 来源：https://developer.apple.com/documentation/SwiftUI/ScaledMetric

抓取时间：2025-12-02T17:34:48Z

---

# ScaledMetric

**Structure**

一个动态属性，用于缩放数值。

## 声明

```swift
@propertyWrapper struct ScaledMetric<Value> where Value : BinaryFloatingPoint
```

## 创建指标

- **init(wrappedValue:)**：使用默认缩放比例，以未缩放值创建缩放后的指标。

- **init(wrappedValue:relativeTo:)**：使用未缩放值和用于缩放的文本样式创建缩放后的指标。

## 获取指标

- **wrappedValue**：根据当前环境缩放后的值。

## 调整文本大小

- **textScale(_:isEnabled:)**：为视图中的文本应用缩放比例。

- **dynamicTypeSize(_:)**：将视图中的动态字体大小设置为给定值。

- **dynamicTypeSize**：当前动态字体大小。

- **DynamicTypeSize**：动态字体大小，指定可缩放内容的大小。

- **TextVariantPreference**：用于控制文本视图大小变体的协议。

- **FixedTextVariant**：默认文本变体首选项，选择最大可用变体。

- **SizeDependentTextVariant**：大小相关的变体首选项允许文本在选择要显示的变体时考虑可用空间。

## 符合以下规范

- DynamicProperty

- Sendable

- SendableMetatype


---
source: https://developer.apple.com/documentation/SwiftUI/ScaledMetric
crawled: 2025-12-02T17:34:48Z
---

# ScaledMetric

**Structure**

A dynamic property that scales a numeric value.

## Declaration

```swift
@propertyWrapper struct ScaledMetric<Value> where Value : BinaryFloatingPoint
```

## Creating the metric

- **init(wrappedValue:)**: Creates the scaled metric with an unscaled value using the default scaling.
- **init(wrappedValue:relativeTo:)**: Creates the scaled metric with an unscaled value and a text style to scale relative to.

## Getting the metric

- **wrappedValue**: The value scaled based on the current environment.

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize(_:)**: Sets the Dynamic Type size within the view to the given value.
- **dynamicTypeSize**: The current Dynamic Type size.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

## Conforms To

- DynamicProperty
- Sendable
- SendableMetatype

