--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/center

抓取时间：2025-12-03T06:36:39Z

---

# center

**类型属性**

用于标记视图水平中心的参考线。

## 声明

```swift
static let center: HorizontalAlignment
```

## 讨论

使用此参考线对齐视图中心：

以下代码使用 [VStack](../VStack.zh-Hans.md) 生成上图：

```swift
struct HorizontalAlignmentCenter: View {
    var body: some View {
        VStack(alignment: .center, spacing: 0) {
            Color.red.frame(width: 1)
            Text("Center").font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

## 获取参考线

- **leading**：用于标记视图前缘的参考线。

- **trailing**：用于标记视图后缘的参考线。

- **listRowSeparatorLeading**：用于标记`List`行分隔符前缘的导向标记。

- **listRowSeparatorTrailing**：用于标记`List`行分隔符后缘的导向标记。


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/center
crawled: 2025-12-03T06:36:39Z
---

# center

**Type Property**

A guide that marks the horizontal center of the view.

## Declaration

```swift
static let center: HorizontalAlignment
```

## Discussion

Use this guide to align the centers of views:



The following code generates the image above using a [VStack](../VStack.zh-Hans.md):

```swift
struct HorizontalAlignmentCenter: View {
    var body: some View {
        VStack(alignment: .center, spacing: 0) {
            Color.red.frame(width: 1)
            Text("Center").font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

## Getting guides

- **leading**: A guide that marks the leading edge of the view.
- **trailing**: A guide that marks the trailing edge of the view.
- **listRowSeparatorLeading**: A guide marking the leading edge of a `List` row separator.
- **listRowSeparatorTrailing**: A guide marking the trailing edge of a `List` row separator.

