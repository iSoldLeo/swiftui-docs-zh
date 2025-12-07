--- 来源：https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/top

抓取时间：2025-12-03T06:36:43Z

---

# top

**类型属性**

用于标记视图顶部边缘的参考线。

## 声明

```swift
static let top: VerticalAlignment
```

## 讨论

使用此参考线对齐视图的顶部边缘：

以下代码使用 [HStack](../HStack.zh-Hans.md) 生成上图：

```swift
struct VerticalAlignmentTop: View {
    var body: some View {
        HStack(alignment: .top, spacing: 0) {
            Color.red.frame(height: 1)
            Text("Top").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## 获取参考线

- **center**：用于标记视图垂直中心的参考线。

- **bottom**：用于标记视图底部边缘的参考线。

- **firstTextBaseline**：用于标记视图中最上方文本基线的参考线。

- **lastTextBaseline**：用于标记视图中最下方文本基线的参考线。


---
source: https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/top
crawled: 2025-12-03T06:36:43Z
---

# top

**Type Property**

A guide that marks the top edge of the view.

## Declaration

```swift
static let top: VerticalAlignment
```

## Discussion

Use this guide to align the top edges of views:



The following code generates the image above using an [HStack](../HStack.zh-Hans.md):

```swift
struct VerticalAlignmentTop: View {
    var body: some View {
        HStack(alignment: .top, spacing: 0) {
            Color.red.frame(height: 1)
            Text("Top").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## Getting guides

- **center**: A guide that marks the vertical center of the view.
- **bottom**: A guide that marks the bottom edge of the view.
- **firstTextBaseline**: A guide that marks the top-most text baseline in a view.
- **lastTextBaseline**: A guide that marks the bottom-most text baseline in a view.

