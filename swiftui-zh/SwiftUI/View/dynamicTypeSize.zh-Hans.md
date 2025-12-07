--- 来源：https://developer.apple.com/documentation/SwiftUI/View/dynamicTypeSize(_:)

抓取时间：2025-12-02T17:34:46Z

---

# dynamicTypeSize(_:)

**实例方法**

将视图中的动态类型大小设置为给定值。

## 声明

```swift
nonisolated func dynamicTypeSize(_ size: DynamicTypeSize) -> some View

```

## 参数

- **size**：要为此视图设置的大小。

## 返回值

将动态类型大小设置为指定值 `size` 的视图。

## 讨论

例如，您可以将动态文字大小设置为 `ContentView` 中的 [xLarge](../DynamicTypeSize/xLarge.zh-Hans.md)（这在预览中非常有用，可以查看不同大小的内容），如下所示：

```swift
ContentView()
    .dynamicTypeSize(.xLarge)
```

如果在设置值后应用了动态文字大小范围，则该值将受该范围的限制：

```swift
ContentView() // Dynamic Type size will be .large
    .dynamicTypeSize(...DynamicTypeSize.large)
    .dynamicTypeSize(.xLarge)
```

限制动态文字大小时，请考虑是否适合添加一个使用 [accessibilityShowsLargeContentViewer()](accessibilityShowsLargeContentViewer.zh-Hans.md) 的大型内容视图。

## 调整文本大小

- **textScale(_:isEnabled:)**：对视图中的文本应用文本缩放。

- **dynamicTypeSize**：当前的动态文字大小。

- **DynamicTypeSize**：动态文字大小，用于指定可缩放内容的大小。

- **ScaledMetric**：用于缩放数值的动态属性。

- **TextVariantPreference**：用于控制文本视图大小变体的协议。

- **FixedTextVariant**：默认文本变体首选项，选择最大可用变体。

- **SizeDependentTextVariant**：大小相关的变体首选项，允许文本在选择要显示的变体时考虑可用空间。


---
source: https://developer.apple.com/documentation/SwiftUI/View/dynamicTypeSize(_:)
crawled: 2025-12-02T17:34:46Z
---

# dynamicTypeSize(_:)

**Instance Method**

Sets the Dynamic Type size within the view to the given value.

## Declaration

```swift
nonisolated func dynamicTypeSize(_ size: DynamicTypeSize) -> some View

```

## Parameters

- **size**: The size to set for this view.

## Return Value

A view that sets the Dynamic Type size to the specified `size`.

## Discussion

As an example, you can set a Dynamic Type size in `ContentView` to be [xLarge](../DynamicTypeSize/xLarge.zh-Hans.md) (this can be useful in previews to see your content at a different size) like this:

```swift
ContentView()
    .dynamicTypeSize(.xLarge)
```

If a Dynamic Type size range is applied after setting a value, the value is limited by that range:

```swift
ContentView() // Dynamic Type size will be .large
    .dynamicTypeSize(...DynamicTypeSize.large)
    .dynamicTypeSize(.xLarge)
```

When limiting the Dynamic Type size, consider if adding a large content view with [accessibilityShowsLargeContentViewer()](accessibilityShowsLargeContentViewer.zh-Hans.md) would be appropriate.

## Adjusting text size

- **textScale(_:isEnabled:)**: Applies a text scale to text in the view.
- **dynamicTypeSize**: The current Dynamic Type size.
- **DynamicTypeSize**: A Dynamic Type size, which specifies how large scalable content should be.
- **ScaledMetric**: A dynamic property that scales a numeric value.
- **TextVariantPreference**: A protocol for controlling the size variant of text views.
- **FixedTextVariant**: The default text variant preference that chooses the largest available variant.
- **SizeDependentTextVariant**: The size dependent variant preference allows the text to take the available space into account when choosing the variant to display.

