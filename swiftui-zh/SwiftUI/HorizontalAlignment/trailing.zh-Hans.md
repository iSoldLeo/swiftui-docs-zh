--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/trailing
抓取时间：2025-12-03T06:36:39Z

---

# 尾部对齐

**类型属性**

用于标记视图尾部边缘的参考线。

## 声明

```swift
static let trailing: HorizontalAlignment
```

## 讨论

使用此参考线对齐视图的尾部边缘。对于使用从左到右语言的设备，尾部边缘位于右侧：

以下代码使用 [VStack](../VStack.zh-Hans.md) 生成上图：

```swift
struct HorizontalAlignmentTrailing: View {
    var body: some View {
        VStack(alignment: .trailing, spacing: 0) {
            Color.red.frame(width: 1)
            Text("Trailing").font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

## 获取参考线

- **leading**：用于标记视图前缘的参考线。

- **center**：用于标记视图水平中心的参考线。

- **listRowSeparatorLeading**：用于标记`List`行分隔符前缘的参考线。

- **listRowSeparatorTrailing**：用于标记`List`行分隔符后缘的参考线。


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/trailing
crawled: 2025-12-03T06:36:39Z
---

# trailing

**Type Property**

A guide that marks the trailing edge of the view.

## Declaration

```swift
static let trailing: HorizontalAlignment
```

## Discussion

Use this guide to align the trailing edges of views. For a device that uses a left-to-right language, the trailing edge is on the right:



The following code generates the image above using a [VStack](../VStack.zh-Hans.md):

```swift
struct HorizontalAlignmentTrailing: View {
    var body: some View {
        VStack(alignment: .trailing, spacing: 0) {
            Color.red.frame(width: 1)
            Text("Trailing").font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

## Getting guides

- **leading**: A guide that marks the leading edge of the view.
- **center**: A guide that marks the horizontal center of the view.
- **listRowSeparatorLeading**: A guide marking the leading edge of a `List` row separator.
- **listRowSeparatorTrailing**: A guide marking the trailing edge of a `List` row separator.

