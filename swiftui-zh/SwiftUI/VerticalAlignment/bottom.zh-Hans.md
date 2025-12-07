--- 来源：https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/bottom
抓取时间：2025-12-03T06:36:45Z

---

# 底部

**类型属性**

用于标记视图底部边缘的参考线。

## 声明

```swift
static let bottom: VerticalAlignment
```

## 讨论

使用此参考线对齐视图的底部边缘：

以下代码使用 [HStack](../HStack.zh-Hans.md) 生成上图：

```swift
struct VerticalAlignmentBottom: View {
    var body: some View {
        HStack(alignment: .bottom, spacing: 0) {
            Color.red.frame(height: 1)
            Text("Bottom").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## 获取参考线

- **top**：用于标记视图顶部边缘的参考线。

- **center**：用于标记视图垂直中心的参考线。

- **firstTextBaseline**：用于标记视图中最上方文本基线的参考线。

- **lastTextBaseline**：用于标记视图中最下方文本基线的参考线。


---
source: https://developer.apple.com/documentation/SwiftUI/VerticalAlignment/bottom
crawled: 2025-12-03T06:36:45Z
---

# bottom

**Type Property**

A guide that marks the bottom edge of the view.

## Declaration

```swift
static let bottom: VerticalAlignment
```

## Discussion

Use this guide to align the bottom edges of views:



The following code generates the image above using an [HStack](../HStack.zh-Hans.md):

```swift
struct VerticalAlignmentBottom: View {
    var body: some View {
        HStack(alignment: .bottom, spacing: 0) {
            Color.red.frame(height: 1)
            Text("Bottom").font(.title).border(.gray)
            Color.red.frame(height: 1)
        }
    }
}
```

## Getting guides

- **top**: A guide that marks the top edge of the view.
- **center**: A guide that marks the vertical center of the view.
- **firstTextBaseline**: A guide that marks the top-most text baseline in a view.
- **lastTextBaseline**: A guide that marks the bottom-most text baseline in a view.

