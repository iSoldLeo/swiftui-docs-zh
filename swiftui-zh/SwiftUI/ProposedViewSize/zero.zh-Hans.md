--- 来源：https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/zero
抓取时间：2025-12-03T06:39:26Z

---

# zero

**类型属性**

一个在两个维度上都包含零的尺寸建议。

## 声明

```swift
static let zero: ProposedViewSize
```

## 讨论

自定义布局的子视图在使用 [dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) 方法建议此值时，会返回其最小尺寸。自定义布局也应该使用 [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) 方法返回此值的最小尺寸。

## 获取标准建议

- **infinity**：一个在两个维度上都包含无穷大的尺寸建议。

- **unspecified**：一个两个维度都未指定的建议尺寸。


---
source: https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/zero
crawled: 2025-12-03T06:39:26Z
---

# zero

**Type Property**

A size proposal that contains zero in both dimensions.

## Declaration

```swift
static let zero: ProposedViewSize
```

## Discussion

Subviews of a custom layout return their minimum size when you propose this value using the [dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) method. A custom layout should also return its minimum size from the [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) method for this value.

## Getting standard proposals

- **infinity**: A size proposal that contains infinity in both dimensions.
- **unspecified**: The proposed size with both dimensions left unspecified.

