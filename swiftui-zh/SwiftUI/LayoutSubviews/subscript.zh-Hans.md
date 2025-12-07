---
来源： https://developer.apple.com/documentation/SwiftUI/LayoutSubviews/subscript(_:)
抓取时间： 2025-12-02T20:59:13Z
---

# 下标(_:)

**实例下标**

获取指定范围内的子视图代理。

## 声明

```swift
subscript(bounds: Range<Int>) -> LayoutSubviews { get }
```

## 访问子视图

- **startIndex**：第一个子视图的索引。
- **endIndex**：第一个子视图的索引：比最后一个子视图高一级的索引。
- **LayoutSubviews.Element**：包含代理值的类型。
- **LayoutSubviews.Index**：包含代理值的类型：可用于索引代理值的类型。
- **LayoutSubviews.SubSequence**：包含代理值子序列的类型。


---
source: https://developer.apple.com/documentation/SwiftUI/LayoutSubviews/subscript(_:)
crawled: 2025-12-02T20:59:13Z
---

# subscript(_:)

**Instance Subscript**

Gets the subview proxies in the specified range.

## Declaration

```swift
subscript(bounds: Range<Int>) -> LayoutSubviews { get }
```

## Accessing subviews

- **startIndex**: The index of the first subview.
- **endIndex**: An index that’s one higher than the last subview.
- **LayoutSubviews.Element**: A type that contains a proxy value.
- **LayoutSubviews.Index**: A type that you can use to index proxy values.
- **LayoutSubviews.SubSequence**: A type that contains a subsequence of proxy values.

