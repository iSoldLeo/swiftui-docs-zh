---
来源： https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior
抓取时间： 2025-12-02T16:49:03Z
---

# 无障碍儿童行为

**Structure**

定义新父元素的子元素的行为。

## 声明

```swift
struct AccessibilityChildBehavior
```

## 获取行为

- **combine**：任何子辅助元素的属性都会合并到新的辅助元素中。
- **contain**：任何子辅助功能元素都会成为新辅助功能元素的子元素。
- **ignore**：任何辅助功能子元素都将被隐藏。

## 创建无障碍元素

- **accessibilityElement(children:)**：创建新的无障碍元素，或修改现有无障碍元素的 [AccessibilityChildBehavior](AccessibilityChildBehavior.zh-Hans.md)。
- **accessibilityChildren(children:)**：用一个或多个新的合成辅助功能元素替换现有辅助功能元素的子元素。
- **accessibilityRepresentation(representation:)**：用新的辅助功能元素替换该视图的一个或多个辅助功能元素。

## 符合

- 等价
- 可散列


---
source: https://developer.apple.com/documentation/SwiftUI/AccessibilityChildBehavior
crawled: 2025-12-02T16:49:03Z
---

# AccessibilityChildBehavior

**Structure**

Defines the behavior for the child elements of the new parent element.

## Declaration

```swift
struct AccessibilityChildBehavior
```

## Getting behaviors

- **combine**: Any child accessibility element’s properties are merged into the new accessibility element.
- **contain**: Any child accessibility elements become children of the new accessibility element.
- **ignore**: Any child accessibility elements become hidden.

## Creating accessible elements

- **accessibilityElement(children:)**: Creates a new accessibility element, or modifies the [AccessibilityChildBehavior](AccessibilityChildBehavior.zh-Hans.md) of the existing accessibility element.
- **accessibilityChildren(children:)**: Replaces the existing accessibility element’s children with one or more new synthetic accessibility elements.
- **accessibilityRepresentation(representation:)**: Replaces one or more accessibility elements for this view with new accessibility elements.

## Conforms To

- Equatable
- Hashable

