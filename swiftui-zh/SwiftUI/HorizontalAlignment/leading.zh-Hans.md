--- 来源：https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/leading

抓取时间：2025-12-03T06:36:38Z

---

# 前导线

**类型属性**

用于标记视图前缘的参考线。

## 声明

```swift
static let leading: HorizontalAlignment
```

## 讨论

使用此参考线对齐视图的前缘。对于使用从左到右语言的设备，前缘位于左侧：

以下代码使用 [VStack](../VStack.zh-Hans.md) 生成上图：

```swift
struct HorizontalAlignmentLeading: View {
    var body: some View {
        VStack(alignment: .leading, spacing: 0) {
            Color.red.frame(width: 1)
            Text("Leading").font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

## 获取参考线

- **center**：用于标记视图水平中心的参考线。

- **trailing**：用于标记视图后缘的参考线。

- **listRowSeparatorLeading**：用于标记 `List` 行分隔符前缘的导向标记。

- **listRowSeparatorTrailing**：用于标记 `List` 行分隔符后缘的导向标记。


---
source: https://developer.apple.com/documentation/SwiftUI/HorizontalAlignment/leading
crawled: 2025-12-03T06:36:38Z
---

# leading

**Type Property**

A guide that marks the leading edge of the view.

## Declaration

```swift
static let leading: HorizontalAlignment
```

## Discussion

Use this guide to align the leading edges of views. For a device that uses a left-to-right language, the leading edge is on the left:



The following code generates the image above using a [VStack](../VStack.zh-Hans.md):

```swift
struct HorizontalAlignmentLeading: View {
    var body: some View {
        VStack(alignment: .leading, spacing: 0) {
            Color.red.frame(width: 1)
            Text("Leading").font(.title).border(.gray)
            Color.red.frame(width: 1)
        }
    }
}
```

## Getting guides

- **center**: A guide that marks the horizontal center of the view.
- **trailing**: A guide that marks the trailing edge of the view.
- **listRowSeparatorLeading**: A guide marking the leading edge of a `List` row separator.
- **listRowSeparatorTrailing**: A guide marking the trailing edge of a `List` row separator.

