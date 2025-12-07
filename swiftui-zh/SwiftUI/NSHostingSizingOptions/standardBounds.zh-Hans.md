---
来源： https://developer.apple.com/documentation/SwiftUI/NSHostingSizingOptions/standardBounds
抓取时间： 2025-12-03T06:57:47Z
---

# 标准边界

**类型属性**

托管视图为其最小、理想和最大尺寸创建约束。

## 声明

```swift
static let standardBounds: NSHostingSizingOptions
```

## 获取尺寸选项

- **intrinsicContentSize**：托管视图创建并更新表示其内容理想尺寸的约束。这些约束反过来又会影响托管视图的`intrinsicContentSize`。
- **maxSize**：托管视图创建和更新表示其内容最大尺寸的约束。
- **minSize**：托管视图创建并更新表示其内容最小大小的约束。
- **preferredContentSize**：托管控制器创建并更新表示其内容理想大小的约束。这些限制反过来又会影响托管控制器的`preferredContentSize`。


---
source: https://developer.apple.com/documentation/SwiftUI/NSHostingSizingOptions/standardBounds
crawled: 2025-12-03T06:57:47Z
---

# standardBounds

**Type Property**

The hosting view creates constraints for its minimum, ideal, and maximum sizes.

## Declaration

```swift
static let standardBounds: NSHostingSizingOptions
```

## Geting sizing options

- **intrinsicContentSize**: The hosting view creates and updates constraints that represent its content’s ideal size. These constraints in turn influence the hosting view’s `intrinsicContentSize`.
- **maxSize**: The hosting view creates and updates constraints that represent its content’s maximum size.
- **minSize**: The hosting view creates and updates constraints that represent its content’s minimum size.
- **preferredContentSize**: The hosting controller creates and updates constraints that represent its content’s ideal size. These constraints in turn influence the hosting controller’s `preferredContentSize`.

