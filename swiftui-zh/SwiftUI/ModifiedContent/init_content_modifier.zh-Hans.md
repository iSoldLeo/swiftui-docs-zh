---
来源：https://developer.apple.com/documentation/SwiftUI/ModifiedContent/init(content:modifier:)
抓取时间：2025-12-02T17:46:34Z
---

# init(content:modifier:)

**Initializer**

定义生成新视图或视图修改器所需的内容和修改器的结构。

### 声明

```swift
nonisolated init(content: Content, modifier: Modifier)
```

## 参数

- **content**：修改器更改的内容。
- **modifier**：应用于内容的修饰符。

## 讨论

如果`content` 是[View](../View.zh-Hans.md)，且`modifier` 是[ViewModifier](../ViewModifier.zh-Hans.md)，则结果是[View](../View.zh-Hans.md)。如果`content` 和 `modifier`都是视图修饰符，那么结果就是将它们组合在一起的新的[ViewModifier](../ViewModifier.zh-Hans.md)。

## 创建修改后的内容视图

- **content**：修改器转换为新视图或新视图修改器的内容。
- **modifier**：视图修改器。


---
source: https://developer.apple.com/documentation/SwiftUI/ModifiedContent/init(content:modifier:)
crawled: 2025-12-02T17:46:34Z
---

# init(content:modifier:)

**Initializer**

A structure that defines the content and modifier needed to produce a new view or view modifier.

## Declaration

```swift
nonisolated init(content: Content, modifier: Modifier)
```

## Parameters

- **content**: The content that the modifier changes.
- **modifier**: The modifier to apply to the content.

## Discussion

If `content` is a [View](../View.zh-Hans.md) and `modifier` is a [ViewModifier](../ViewModifier.zh-Hans.md), the result is a [View](../View.zh-Hans.md). If `content` and `modifier` are both view modifiers, then the result is a new [ViewModifier](../ViewModifier.zh-Hans.md) combining them.

## Creating a modified content view

- **content**: The content that the modifier transforms into a new view or new view modifier.
- **modifier**: The view modifier.

