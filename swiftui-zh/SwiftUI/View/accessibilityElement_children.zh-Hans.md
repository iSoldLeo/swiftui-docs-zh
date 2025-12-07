--- 来源：https://developer.apple.com/documentation/SwiftUI/View/accessibilityElement(children:)

抓取时间：2025-12-02T16:49:01Z

---

# accessibilityElement(children:)

**实例方法**

创建新的辅助功能元素，或修改现有辅助功能元素的 [AccessibilityChildBehavior](../AccessibilityChildBehavior.zh-Hans.md)。

## 声明

```swift
nonisolated func accessibilityElement(children: AccessibilityChildBehavior = .ignore) -> some View

```

## 参数

- **children**：创建或转换辅助功能元素时要使用的行为。默认值为 [ignore](../AccessibilityChildBehavior/ignore.zh-Hans.md)

## 讨论

另请参阅：

- [ignore](../AccessibilityChildBehavior/ignore.zh-Hans.md)

- [combine](../AccessibilityChildBehavior/combine.zh-Hans.md)

- [contain](../AccessibilityChildBehavior/contain.zh-Hans.md)

## 创建辅助功能元素

- **accessibilityChildren(children:)**：将现有辅助功能元素的子元素替换为一个或多个新的合成辅助功能元素。

- **accessibilityRepresentation(representation:)**：将此视图中的一个或多个辅助功能元素替换为新的辅助功能元素。

- **AccessibilityChildBehavior**：定义新父元素的子元素的行为。


---
source: https://developer.apple.com/documentation/SwiftUI/View/accessibilityElement(children:)
crawled: 2025-12-02T16:49:01Z
---

# accessibilityElement(children:)

**Instance Method**

Creates a new accessibility element, or modifies the [AccessibilityChildBehavior](../AccessibilityChildBehavior.zh-Hans.md) of the existing accessibility element.

## Declaration

```swift
nonisolated func accessibilityElement(children: AccessibilityChildBehavior = .ignore) -> some View

```

## Parameters

- **children**: The behavior to use when creating or transforming an accessibility element. The default is [ignore](../AccessibilityChildBehavior/ignore.zh-Hans.md)

## Discussion

See also:

- [ignore](../AccessibilityChildBehavior/ignore.zh-Hans.md)
- [combine](../AccessibilityChildBehavior/combine.zh-Hans.md)
- [contain](../AccessibilityChildBehavior/contain.zh-Hans.md)

## Creating accessible elements

- **accessibilityChildren(children:)**: Replaces the existing accessibility element’s children with one or more new synthetic accessibility elements.
- **accessibilityRepresentation(representation:)**: Replaces one or more accessibility elements for this view with new accessibility elements.
- **AccessibilityChildBehavior**: Defines the behavior for the child elements of the new parent element.

