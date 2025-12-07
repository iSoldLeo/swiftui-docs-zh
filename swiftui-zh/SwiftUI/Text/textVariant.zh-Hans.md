--- 来源：https://developer.apple.com/documentation/SwiftUI/Text/textVariant(_:)

抓取时间：2025-12-01T02:39:37Z

---

# textVariant(_:)

**实例方法**

控制文本大小变体的选择方式。

## 声明

```swift
func textVariant<V>(_ preference: V) -> some View where V : TextVariantPreference

```

## 说明

某些类型的文本，例如 `Text(_:format:)`，可以生成不同大小的字符串，以更好地适应可用空间。默认情况下，所有文本都使用最宽的可用变体。将变体设置为 [sizeDependent](../TextVariantPreference/sizeDependent.zh-Hans.md) 可以让文本在选择要显示的内容时考虑可用空间。


---
source: https://developer.apple.com/documentation/SwiftUI/Text/textVariant(_:)
crawled: 2025-12-01T02:39:37Z
---

# textVariant(_:)

**Instance Method**

Controls the way text size variants are chosen.

## Declaration

```swift
func textVariant<V>(_ preference: V) -> some View where V : TextVariantPreference

```

## Discussion

Certain types of text, such as `Text(_:format:)`, can generate strings of different size to better fit the available space. By default, all text uses the widest available variant. Setting the variant to be [sizeDependent](../TextVariantPreference/sizeDependent.zh-Hans.md) allows the text to take the available space into account when choosing what content to display.

