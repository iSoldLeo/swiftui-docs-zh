--- 来源：https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/lastTextBaseline
抓取时间：2025-12-03T06:36:47Z

---

# lastTextBaseline

**类型属性**

用于标记视图中最底部文本基线的参考线。

## 声明

```swift
static let lastTextBaseline: VerticalAlignment
```

## 讨论

使用此参考线可与视图中最底部文本的基线对齐。此参考线与不包含任何文本的视图的底部对齐。

以下代码使用 [HStack](../HStack.zh-Hans.md) 生成上图：

```swift
struct VerticalAlignmentLastTextBaseline: View {
    var body: some View {
        HStack(alignment: .lastTextBaseline, spacing: 0) {
            Color.red.frame(height: 1)
            Text("Last Text Baseline").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## 获取参考线

- **top**：用于标记视图顶部边缘的参考线。

- **center**：用于标记视图垂直中心的参考线。

- **bottom**：用于标记视图底部边缘的参考线。

- **firstTextBaseline**：用于标记视图中最顶部文本基线的参考线。


---
source: https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/lastTextBaseline
crawled: 2025-12-03T06:36:47Z
---

# lastTextBaseline

**Type Property**

A guide that marks the bottom-most text baseline in a view.

## Declaration

```swift
static let lastTextBaseline: VerticalAlignment
```

## Discussion

Use this guide to align with the baseline of the bottom-most text in a view. The guide aligns with the bottom of a view that contains no text.



The following code generates the image above using an [HStack](../HStack.zh-Hans.md):

```swift
struct VerticalAlignmentLastTextBaseline: View {
    var body: some View {
        HStack(alignment: .lastTextBaseline, spacing: 0) {
            Color.red.frame(height: 1)
            Text("Last Text Baseline").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## Getting guides

- **top**: A guide that marks the top edge of the view.
- **center**: A guide that marks the vertical center of the view.
- **bottom**: A guide that marks the bottom edge of the view.
- **firstTextBaseline**: A guide that marks the top-most text baseline in a view.

