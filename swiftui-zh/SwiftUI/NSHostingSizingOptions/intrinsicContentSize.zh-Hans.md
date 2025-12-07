---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingSizingOptions/intrinsicContentSize
抓取时间： 2025-12-03T06:57:43Z
---

# 本征内容大小

**类型属性**

托管视图创建和更新表示其内容理想大小的约束。这些约束反过来会影响托管视图的 `intrinsicContentSize`。

## 声明

```swift
static let intrinsicContentSize: NSHostingSizingOptions
```

## 讨论

约束条件反映了适合`.unspecified` 提案的大小。

## 获取大小选项

- **maxSize**：托管视图创建和更新表示其内容最大尺寸的约束。
- **minSize**：托管视图创建并更新表示其内容最小大小的约束。
- **preferredContentSize**：托管控制器创建并更新表示其内容理想大小的约束。这些限制反过来又会影响托管控制器的`preferredContentSize`。
- **standardBounds**：托管视图为其最小、理想和最大尺寸创建约束。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSizingOptions/intrinsicContentSize
crawled: 2025-12-03T06:57:43Z
---

# intrinsicContentSize

**Type Property**

The hosting view creates and updates constraints that represent its content’s ideal size. These constraints in turn influence the hosting view’s `intrinsicContentSize`.

## Declaration

```swift
static let intrinsicContentSize: NSHostingSizingOptions
```

## Discussion

The constraints reflect the size that fits a proposal of `.unspecified`.

## Geting sizing options

- **maxSize**: The hosting view creates and updates constraints that represent its content’s maximum size.
- **minSize**: The hosting view creates and updates constraints that represent its content’s minimum size.
- **preferredContentSize**: The hosting controller creates and updates constraints that represent its content’s ideal size. These constraints in turn influence the hosting controller’s `preferredContentSize`.
- **standardBounds**: The hosting view creates constraints for its minimum, ideal, and maximum sizes.

