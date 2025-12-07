--- 来源：https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/infinity
抓取时间：2025-12-03T06:39:26Z

---

# infinity

**类型属性**

一个在两个维度上都包含无穷大的尺寸建议。

## 声明

```swift
static let infinity: ProposedViewSize
```

## 讨论

此尺寸建议在两个维度上都包含 doc://com.apple.documentation/documentation/CoreFoundation/CGFloat/1454161-infinity。当您使用 [dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) 方法建议此值时，自定义布局的子视图将返回其最大尺寸。自定义布局也应使用 [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) 方法返回此值的最大尺寸。

## 获取标准尺寸建议

- **zero**：尺寸建议中两个维度均为零。

- **unspecified**：尺寸建议中两个维度均未指定。


---
source: https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/infinity
crawled: 2025-12-03T06:39:26Z
---

# infinity

**Type Property**

A size proposal that contains infinity in both dimensions.

## Declaration

```swift
static let infinity: ProposedViewSize
```

## Discussion

Both dimensions contain doc://com.apple.documentation/documentation/CoreFoundation/CGFloat/1454161-infinity in this size proposal. Subviews of a custom layout return their maximum size when you propose this value using the [dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) method. A custom layout should also return its maximum size from the [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) method for this value.

## Getting standard proposals

- **zero**: A size proposal that contains zero in both dimensions.
- **unspecified**: The proposed size with both dimensions left unspecified.

