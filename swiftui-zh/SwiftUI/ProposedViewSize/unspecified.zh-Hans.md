--- 来源：https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/unspecified
抓取时间：2025-12-03T06:39:27Z

---

# unspecified

**类型属性**

两个维度均未指定的建议尺寸。

## 声明

```swift
static let unspecified: ProposedViewSize
```

## 讨论

此尺寸建议的两个维度均包含 `nil`。自定义布局的子视图在使用 [dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) 方法建议此值时，会返回其理想尺寸。自定义布局也应使用 [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) 方法返回此值的理想尺寸。

## 获取标准建议

- **zero**：两个维度均包含零的尺寸建议。

- **infinity**：一个包含两个维度无穷大的尺寸方案。


---
source: https://developer.apple.com/documentation/SwiftUI/ProposedViewSize/unspecified
crawled: 2025-12-03T06:39:27Z
---

# unspecified

**Type Property**

The proposed size with both dimensions left unspecified.

## Declaration

```swift
static let unspecified: ProposedViewSize
```

## Discussion

Both dimensions contain `nil` in this size proposal. Subviews of a custom layout return their ideal size when you propose this value using the [dimensions(in:)](../LayoutSubview/dimensions_in.zh-Hans.md) method. A custom layout should also return its ideal size from the [sizeThatFits(proposal:subviews:cache:)](../Layout/sizeThatFits_proposal_subviews_cache.zh-Hans.md) method for this value.

## Getting standard proposals

- **zero**: A size proposal that contains zero in both dimensions.
- **infinity**: A size proposal that contains infinity in both dimensions.

