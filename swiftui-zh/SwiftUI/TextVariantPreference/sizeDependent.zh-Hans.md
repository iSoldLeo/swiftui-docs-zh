---
来源： https://developer.apple.com/documentation/SwiftUI/TextVariantPreference/sizeDependent
抓取时间：2025-12-03T06:18:37Z
---

# 大小取决于

**类型属性**

尺寸相关首选项允许文本在选择要显示的尺寸变量时考虑可用空间。

## 声明

```swift
static var sizeDependent: SizeDependentTextVariant { get }
```

## 讨论

当[Text](../Text.zh-Hans.md) 为其内容提供不同大小的选项时，大小相关首选项会选择适合可用空间的最大选项，而不会截断或剪切其内容。



## 与 ViewThatFits 的区别

[sizeDependent](sizeDependent.zh-Hans.md)文本变体首选项在用法和行为上都与[ViewThatFits](../ViewThatFits.zh-Hans.md)不同。[ViewThatFits](../ViewThatFits.zh-Hans.md)会选择**ideal**大小适合可用空间的第一个子代。对于[Text](../Text.zh-Hans.md)来说，这意味着它只会选择能将其内容放入可用空间**且不换行**的文本。另一方面，如果使用文本变体首选项，则会选择既能满足可用空间又能遵守所有常规布局规则的最大变体，例如[lineLimit](../EnvironmentValues/lineLimit.zh-Hans.md)。

要使用[ViewThatFits](../ViewThatFits.zh-Hans.md)，就必须提供多个不同的视图作为不同大小的选项。有了这种文本变体偏好，单个[Text](../Text.zh-Hans.md) 本身就能提供不同的尺寸变体。生成这些尺寸变量的方式以及可用的尺寸变量数量取决于所使用的文本初始化器。


---
source: https://developer.apple.com/documentation/SwiftUI/TextVariantPreference/sizeDependent
crawled: 2025-12-03T06:18:37Z
---

# sizeDependent

**Type Property**

The size dependent preference allows the text to take the available space into account when choosing the size variant to display.

## Declaration

```swift
static var sizeDependent: SizeDependentTextVariant { get }
```

## Discussion

When a [Text](../Text.zh-Hans.md) provides different size options for its content, the size dependent preference chooses the largest option that fits into the available space without truncating or clipping its content.



## Difference to ViewThatFits

The [sizeDependent](sizeDependent.zh-Hans.md) text variant preference differs from [ViewThatFits](../ViewThatFits.zh-Hans.md) both in usage and in behavior. [ViewThatFits](../ViewThatFits.zh-Hans.md) chooses the first child where the **ideal** size fits the available space. For [Text](../Text.zh-Hans.md) this means that it will only choose texts that can fit their contents into the available space **without a line break**. With this text variant preference, on the other hand, the largest variant is chosen that can fit the available space while respecting all the regular layout rules, such as [lineLimit](../EnvironmentValues/lineLimit.zh-Hans.md).

To use [ViewThatFits](../ViewThatFits.zh-Hans.md), multiple different views have to be provided as the different size options. With this text variant preference, a single [Text](../Text.zh-Hans.md) provides the different size variants intrinsically. The way it generates these size variants and how many size variants are available depends on the text initializer used.

