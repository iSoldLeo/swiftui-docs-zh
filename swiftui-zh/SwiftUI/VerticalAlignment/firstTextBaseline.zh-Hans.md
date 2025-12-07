--- 来源：https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/firstTextBaseline

抓取时间：2025-12-03T06:36:46Z

---

# firstTextBaseline

**类型属性**

用于标记视图中最顶部文本基线的参考线。

## 声明

```swift
static let firstTextBaseline: VerticalAlignment
```

## 讨论

使用此参考线可与视图中最顶部文本的基线对齐。如果视图中不包含任何文本，则参考线将与视图底部对齐：

以下代码使用 [HStack](../HStack.zh-Hans.md) 生成上图：

```swift
struct VerticalAlignmentFirstTextBaseline: View {
    var body: some View {
        HStack(alignment: .firstTextBaseline, spacing: 0) {
            Color.red.frame(height: 1)
            Text("First Text Baseline").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## 获取参考线

- **top**：用于标记视图顶部边缘的参考线。

- **center**：用于标记视图垂直中心的参考线。

- **bottom**：用于标记视图底部边缘的参考线。

- **lastTextBaseline**：用于标记视图中最底部文本基线的参考线。


---
source: https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/firstTextBaseline
crawled: 2025-12-03T06:36:46Z
---

# firstTextBaseline

**Type Property**

A guide that marks the top-most text baseline in a view.

## Declaration

```swift
static let firstTextBaseline: VerticalAlignment
```

## Discussion

Use this guide to align with the baseline of the top-most text in a view. The guide aligns with the bottom of a view that contains no text:



The following code generates the image above using an [HStack](../HStack.zh-Hans.md):

```swift
struct VerticalAlignmentFirstTextBaseline: View {
    var body: some View {
        HStack(alignment: .firstTextBaseline, spacing: 0) {
            Color.red.frame(height: 1)
            Text("First Text Baseline").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## Getting guides

- **top**: A guide that marks the top edge of the view.
- **center**: A guide that marks the vertical center of the view.
- **bottom**: A guide that marks the bottom edge of the view.
- **lastTextBaseline**: A guide that marks the bottom-most text baseline in a view.

